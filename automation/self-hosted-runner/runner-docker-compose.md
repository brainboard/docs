# Deploy runner with docker-compose

### Pre-requisites

First, you need to have Docker installed on your server. If not already installed, please follow instructions from [this page](https://docs.docker.com/engine/install/).

After installing Docker, you need the following files in a directory:

{% code title="docker-compose.yml" fullWidth="false" %}
```yaml
services:
  runner:
    image: ghcr.io/brainboard/runner:next
    # You can also pin the version using any Brainboard version from our changelog (https://docs.brainboard.co/changelog)
    # image: ghcr.io/brainboard/runner:2026.07.1
    restart: unless-stopped
    command: /brainboard-runner
    volumes:
      - "/var/run/docker.sock:/var/run/docker.sock"
      - "./runner-config.yaml:/etc/brainboard-runner/config.yaml:ro"
      - "/tmp:/tmp"
```
{% endcode %}

{% code title="runner-config.yaml" fullWidth="false" %}
```yml
log: 
  level: warn

runner:
  name: "self-hosted runner"
  token: "your-runner-token"

# API Base url (default to https://api.us1.brainboard.co)
# api:
#  endpoint: "https://api.apac1.brainboard.co"
```
{% endcode %}

<details>

<summary>Full configuration example</summary>

#### Configuration

| Key                             | Section    | Required       | Type     | Possible Values                           | Default                                        |
| ------------------------------- | ---------- | -------------- | -------- | ----------------------------------------- | ---------------------------------------------- |
| `log.level`                     | `log`      | Optional       | string   | `trace`, `debug`, `info`, `warn`, `error` | `info`                                         |
| `log.format`                    | `log`      | Optional       | string   | `json`, `pretty`                          | `json`                                         |
| `runner.name`                   | `runner`   | **Required**   | string   | any string                                | —                                              |
| `runner.token`                  | `runner`   | **Required**\* | string   | any string                                | `$RUNNER_TOKEN` env var                        |
| `runner.concurrency`            | `runner`   | Optional       | integer  | `1`–`255`                                 | `4`                                            |
| `runner.temporary_dir`          | `runner`   | Optional       | string   | any path                                  | `$RUNNER_TEMP_DIR` or `/tmp/brainboard-runner` |
| `runner.poll_interval`          | `runner`   | Optional       | duration | e.g. `10s`, `1m`                          | `10s`                                          |
| `runner.max_job_wait_time`      | `runner`   | Optional       | duration | e.g. `1s`, `500ms`                        | `1s`                                           |
| `runner.job_max_execution_time` | `runner`   | Optional       | duration | e.g. `240m`, `4h`                         | `240m`                                         |
| `api.endpoint`                  | `api`      | Optional       | string   | any URL                                   | `https://api.us1.brainboard.co`                |
| `api.http_timeout`              | `api`      | Optional       | duration | e.g. `30s`, `2m`                          | `60s`                                          |
| `executor.docker.worker_image`  | `executor` | Optional       | string   | any Docker image reference                | `ghcr.io/brainboard/plugins/worker:latest`     |
| `executor.docker.ecr_region`    | `executor` | Optional       | string   | any AWS region                            | `$AWS_REGION` env var or `us-east-1`           |
| `metrics.enabled`               | `metrics`  | Optional       | boolean  | `true`, `false`                           | `true`                                         |
| `metrics.hostname`              | `metrics`  | Optional       | string   | any bind address                          | `0.0.0.0`                                      |
| `metrics.port`                  | `metrics`  | Optional       | integer  | `1`–`65535`                               | `9090`                                         |

* \* **runner.token** must be provided either in the config file or via the `RUNNER_TOKEN` environment variable.
* Duration fields accept suffixes: `ms`, `s`, `m`, `h`, `d` (e.g. `500ms`, `30s`, `5m`, `2h`, `1d`).



#### Full example of runner-config.yaml

{% code title="runner-config.yaml" %}
```yaml
log:
  level: debug
  format: json          # optional: json (default) or pretty

runner:
  name: "my-runner"
  token: "my-token"
  concurrency: 4
  poll_interval: 20s
  max_job_wait_time: 1s
  job_max_execution_time: 240m
  temporary_dir: "/tmp/brainboard-runner"

api:
  endpoint: "https://api.us1.brainboard.co"
  http_timeout: 60s

executor:
  docker:
    worker_image: "ghcr.io/brainboard/plugins/worker:latest"
```
{% endcode %}

</details>

<details>

<summary>Runner migration (&#x3C; 2026.07.1)</summary>

1. In `docker-compose.yml`, update both the image tag and command:

```diff
-    image: ghcr.io/brainboard/runner:2026.02.3
+    image: ghcr.io/brainboard/runner:latest # or 2026.07.1
     restart: unless-stopped
-    command: /brainboard-runner run
+    command: /brainboard-runner
```

2. Replace your `runner-config.yaml` with the one above, here are the required updates:

Notable changes for `runner-config.yaml`:

* **Duration format**: All duration fields (`poll_interval`, `http_timeout`, `max_job_wait_time`, `job_max_execution_time`) now require an explicit unit suffix (e.g. `20s`, `60s`, `240m`). Raw integers are not accepted.
* **ECR authentication**: The `ecr_auth` flag is removed. ECR credentials are fetched automatically whenever the `worker_image` URL points to an ECR registry (hostname ending in `.dkr.ecr.*.amazonaws.com`).
* **Log level override**: The `--level` / `-l` CLI flag and the `LOG_LEVEL` environment variable still override `log.level` at startup.

```diff
-level: warn
+log:
+  level: warn

 runner:
-  poll_interval: 5
+  poll_interval: 5s
```

3. Then restart your runner: `docker compose up -d`  / `docker compose up -d --force-recreate`



</details>

### Configuration

The `runner-config.yaml` file contains the Brainboard runner configuration. You can modify this file to change the configuration of the runner. It's important to note that the `runner-config.yaml` file should be in the same directory as the `docker-compose.yml` file.

Before starting the runner for the first time, it is mandatory to update the `runner.token` configuration value in the `runner-config.yaml` file. Update this value with the private self-hosted runner token you generated from the Brainboard settings page.

```yaml
runner:
  token: "your-runner-token"
```

This token should be unique and cannot be shared across multiple runners. If you use the same token on multiple runners, you will encounter issues when running CI/CD jobs.

### Starting the runner

To start the runner, open a terminal and navigate to the directory where you downloaded the docker-compose and runner-config files. The following command will start the runner in the background:

```bash
docker compose up -d
```

Then, you can check on Brainboard's dashboard the last heartbeat and the status.

### Usage

If you want to see the logs, you can run this command:

```bash
docker compose logs -f
```

To stop the Brainboard runner, execute the following command:

```bash
docker compose down
```
