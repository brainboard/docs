# Deploy runner with docker-compose

### Pre-requisites

First of all, you need to have Docker installed on your server. If not already installed, please follow instructions from [this page](https://docs.docker.com/engine/install/).

After installing Docker, you need to download the following files in a directory:

* [docker-compose.yml](https://gitlab.com/brainboard/brainboard/-/blob/main/runner-assets/docker-compose.yaml)
* [runner-config.yml](https://gitlab.com/brainboard/brainboard/-/blob/main/runner-assets/runner-config.yaml)

### Configuration

The `runner-config.yaml` file contains Brainboard runner configuration. You can modify this file to change the configuration of the runner. It's important to note that the `runner-config.yaml` file should be in the same directory as the `docker-compose.yml` file.

Before starting the runner for the first time, it is mandatory to update the `runner.token` configuration value in the `runner-config.yaml` file. Update this value with the private self-hosted runner token you generated from the Brainboard settings page.

```yaml
...
runner:
  token: "your-runner-token"
...
```

This token should be unique and cannot be shared across multiple runners. If you use the same token on multiple runners, you will encounter issues when running CI/CD jobs.

### Starting the runner

To start the runner, open a terminal and navigate to the directory where you downloaded the docker-compose and runner-config files. The following command will start the runner in the background:

```bash
docker compose up -d
```

#### Register runner with your organization

Once the runner is started, you will need to register it with your organization. To do so, open a terminal inside the runner container (see below) and run the following command:

```bash
/brainboard-runner register
```

This operation only needs to be done once, when the runner is started for the first time.

### Usage

To open a terminal inside the runner container, use the following command:

```bash
docker compose exec runner sh
```

If you want to see the logs, you can run this command:

```bash
docker compose logs -f
```

To stop the Brainboard runner, execute the following command:

```bash
docker compose down
```
