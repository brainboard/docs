# Deploy runner with Docker-Compose

### Pre-requisites

First, you need to have **Docker** installed on your server. If not already installed, please follow the instructions on [this page](https://docs.docker.com/engine/install/).

After installing **Docker**, you need the following files in a directory:

{% code title="docker-compose.yml" fullWidth="false" %}
```yaml
services:
  runner:
    image: ghcr.io/brainboard/runner:latest
    # You can also pin the version using any Brainboard version from our changelog (https://docs.brainboard.co/changelog)
    # image: ghcr.io/brainboard/runner:2026.06.9
    restart: unless-stopped
    command: [ "/brainboard-runner" ]
    stop_grace_period: 240s
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

<table><thead><tr><th width="173.66668701171875">Key</th><th width="100.0001220703125">Section</th><th width="105.999755859375">Required</th><th width="86.666748046875">Type</th><th width="128">Possible Values</th><th>Default</th></tr></thead><tbody><tr><td><mark style="color:$primary;"><strong><code>log.level</code></strong></mark></td><td><strong><code>log</code></strong></td><td><sub>Optional</sub></td><td><sub>string</sub></td><td><mark style="color:blue;"><strong><code>trace</code></strong></mark>, <mark style="color:blue;"><strong><code>debug</code></strong></mark>, <mark style="color:blue;"><strong><code>info</code></strong></mark>, <mark style="color:orange;"><strong><code>warn</code></strong></mark>, <mark style="color:red;"><strong><code>error</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>info</code></strong></mark></td></tr><tr><td><sub><mark style="color:$primary;"><strong><code>log.format</code></strong></mark></sub></td><td><strong><code>log</code></strong></td><td><sub>Optional</sub></td><td><sub>string</sub></td><td><mark style="color:blue;"><strong><code>json</code></strong></mark>, <mark style="color:blue;"><strong><code>pretty</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>json</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>runner.name</code></strong></mark></td><td><strong><code>runner</code></strong></td><td><sub><mark style="color:red;"><strong>Required</strong></mark></sub></td><td><sub>string</sub></td><td>any string</td><td>—</td></tr><tr><td><mark style="color:$primary;"><strong><code>runner.token</code></strong></mark></td><td><strong><code>runner</code></strong></td><td><sub><mark style="color:red;"><strong>Required</strong></mark></sub></td><td><sub>string</sub></td><td>any string</td><td><mark style="color:$primary;"><strong><code>$RUNNER_TOKEN</code></strong></mark> env var</td></tr><tr><td><mark style="color:$primary;"><strong><code>runner.concurrency</code></strong></mark></td><td><strong><code>runner</code></strong></td><td><sub>Optional</sub></td><td><sub>integer</sub></td><td><mark style="color:blue;"><strong><code>1</code></strong><strong>–</strong><strong><code>255</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>4</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>runner.temporary_dir</code></strong></mark></td><td><strong><code>runner</code></strong></td><td><sub>Optional</sub></td><td><sub>string</sub></td><td><sub>any path</sub></td><td><mark style="color:$primary;"><strong><code>$RUNNER_TEMP_DIR</code></strong></mark> or <mark style="color:$primary;"><strong><code>/tmp/brainboard-runner</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>runner.poll_interval</code></strong></mark></td><td><strong><code>runner</code></strong></td><td><sub>Optional</sub></td><td><sub>duration</sub></td><td>e.g. <mark style="color:blue;"><strong><code>10s</code></strong></mark>, <mark style="color:blue;"><strong><code>1m</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>10s</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>runner.max_job_wait_time</code></strong></mark></td><td><strong><code>runner</code></strong></td><td><sub>Optional</sub></td><td><sub>duration</sub></td><td>e.g. <mark style="color:blue;"><strong><code>1s</code></strong></mark>, <mark style="color:blue;"><strong><code>500ms</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>1s</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>runner.job_max_execution_time</code></strong></mark></td><td><strong><code>runner</code></strong></td><td><sub>Optional</sub></td><td><sub>duration</sub></td><td>e.g. <mark style="color:blue;"><strong><code>240m</code></strong></mark>, <mark style="color:blue;"><strong><code>4h</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>240m</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>api.endpoint</code></strong></mark></td><td><strong><code>api</code></strong></td><td><sub>Optional</sub></td><td><sub>string</sub></td><td><sub>any URL</sub></td><td><mark style="color:$primary;"><strong><code>https://api.us1.brainboard.co</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>api.http_timeout</code></strong></mark></td><td><strong><code>api</code></strong></td><td><sub>Optional</sub></td><td><sub>duration</sub></td><td>e.g. <mark style="color:blue;"><strong><code>30s</code></strong></mark>, <mark style="color:blue;"><strong><code>2m</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>60s</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>executor.docker.worker_image</code></strong></mark></td><td><strong><code>executor</code></strong></td><td><sub>Optional</sub></td><td><sub>string</sub></td><td><sub>any <strong>Docker</strong> image reference</sub></td><td><mark style="color:$primary;"><strong><code>ghcr.io/brainboard/plugins/worker:latest</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>executor.docker.ecr_region</code></strong></mark></td><td><strong><code>executor</code></strong></td><td><sub>Optional</sub></td><td><sub>string</sub></td><td><sub>any <strong>AWS</strong> region</sub></td><td><mark style="color:$primary;"><strong><code>$AWS_REGION</code></strong></mark> env var or <mark style="color:$primary;"><strong><code>us-east-1</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>metrics.enabled</code></strong></mark></td><td><strong><code>metrics</code></strong></td><td><sub>Optional</sub></td><td><sub>boolean</sub></td><td><mark style="color:blue;"><strong><code>true</code></strong></mark>, <mark style="color:red;"><strong><code>false</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>true</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>metrics.hostname</code></strong></mark></td><td><strong><code>metrics</code></strong></td><td><sub>Optional</sub></td><td><sub>string</sub></td><td><sub>any bind address</sub></td><td><mark style="color:$primary;"><strong><code>0.0.0.0</code></strong></mark></td></tr><tr><td><mark style="color:$primary;"><strong><code>metrics.port</code></strong></mark></td><td><strong><code>metrics</code></strong></td><td><sub>Optional</sub></td><td><sub>integer</sub></td><td><mark style="color:blue;"><strong><code>1</code></strong><strong>–</strong><strong><code>65535</code></strong></mark></td><td><mark style="color:$primary;"><strong><code>9090</code></strong></mark></td></tr></tbody></table>

* <mark style="color:red;">\*</mark>**runner.token** must be provided either in the config file or via the <mark style="color:blue;">**`RUNNER_TOKEN`**</mark> environment variable.
* Duration fields accept suffixes: <mark style="color:blue;">**`ms`**</mark><mark style="color:blue;">**,**</mark><mark style="color:blue;">**&#x20;**</mark><mark style="color:blue;">**`s`**</mark><mark style="color:blue;">**,**</mark><mark style="color:blue;">**&#x20;**</mark><mark style="color:blue;">**`m`**</mark><mark style="color:blue;">**,**</mark><mark style="color:blue;">**&#x20;**</mark><mark style="color:blue;">**`h`**</mark><mark style="color:blue;">**,**</mark><mark style="color:blue;">**&#x20;**</mark><mark style="color:blue;">**`d`**</mark> (e.g. **`500ms`, `30s`, `5m`, `2h`, `1d`**).

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

<summary>Runner migration (&#x3C; 2026.06.7)</summary>

1. In <mark style="color:blue;">**`docker-compose.yml`**</mark>, update both the image tag and command:

```diff
-    image: ghcr.io/brainboard/runner:2026.02.3
+    image: ghcr.io/brainboard/runner:latest # or 2026.06.9
     restart: unless-stopped
-    command: /brainboard-runner run
+    command: /brainboard-runner
```

2. Replace your <mark style="color:blue;">**`runner-config.yaml`**</mark> with the one above; here are the required updates:

Notable changes for <mark style="color:blue;">**`runner-config.yaml`**</mark>:

* **Duration format**: All duration fields (<mark style="color:$primary;">**`poll_interval`**</mark>, <mark style="color:$primary;">**`http_timeout`**</mark>, <mark style="color:$primary;">**`max_job_wait_time`**</mark>, <mark style="color:$primary;">**`job_max_execution_time`**</mark>) now require an explicit unit suffix (e.g. <mark style="color:$primary;">**`20s`**</mark><mark style="color:$primary;">**,**</mark><mark style="color:$primary;">**&#x20;**</mark><mark style="color:$primary;">**`60s`**</mark><mark style="color:$primary;">**,**</mark><mark style="color:$primary;">**&#x20;**</mark><mark style="color:$primary;">**`240m`**</mark>). Raw integers are not accepted.
* **ECR authentication**: The <mark style="color:$primary;">**`ecr_auth`**</mark> flag is removed. ECR credentials are fetched automatically whenever the <mark style="color:$primary;">**`worker_image`**</mark> URL points to an ECR registry (hostname ending in <mark style="color:blue;">**`.dkr.ecr.*.amazonaws.com`**</mark>).
* **Log level override**: The <mark style="color:blue;">**`--level`**</mark> / <mark style="color:blue;">**`-l`**</mark> CLI flag and the <mark style="color:blue;">**`LOG_LEVEL`**</mark> environment variable still override <mark style="color:blue;">**`log.level`**</mark> at startup.

```diff
-level: warn
+log:
+  level: warn

 runner:
-  poll_interval: 5
+  poll_interval: 5s
```

3. Then restart your runner: <mark style="color:blue;">**`docker compose up -d`**</mark> / <mark style="color:blue;">**`docker compose up -d --force-recreate`**</mark>

</details>

### Configuration

The <mark style="color:blue;">**`runner-config.yaml`**</mark> file contains the <mark style="color:$primary;">**Brainboard**</mark> runner configuration. You can modify this file to change the runner's configuration. It's important to note that the <mark style="color:blue;">**`runner-config.yaml`**</mark> file should be in the same directory as the <mark style="color:blue;">**`docker-compose.yml`**</mark> file.

Before starting the runner for the first time, it is mandatory to update the <mark style="color:blue;">**`runner.token`**</mark> configuration value in the <mark style="color:blue;">**`runner-config.yaml`**</mark> file. Update this value with the private self-hosted runner token you generated from the <mark style="color:$primary;">**Brainboard**</mark> settings page.

```yaml
runner:
  token: "your-runner-token"
```

This token should be unique and <mark style="color:red;">**cannot**</mark> be shared **across multiple runners**. If you use the same token on multiple runners, you will encounter issues when running **CI/CD** jobs.

### Starting the runner

To start the runner, open a terminal and navigate to the directory where you downloaded the docker-compose and runner-config files. The following command will start the runner in the background:

```bash
docker compose up -d
```

Then, you can check on <mark style="color:$primary;">**Brainboard's**</mark> dashboard the last heartbeat and the status.

### Usage

If you want to see the logs, you can run this command:

```bash
docker compose logs -f
```

To stop the <mark style="color:$primary;">**Brainboard**</mark> runner, execute the following command:

```bash
docker compose down
```
