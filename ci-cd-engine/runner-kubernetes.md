# Deploy runner with kubernetes

### Pre-requisites

* A running Kubernetes cluster
* [Helm](https://helm.sh/docs/intro/install) installed locally
* Kubectl installed locally

Brainboard provides a Helm chart to deploy the runner in your existing Kubernetes cluster.

The Helm chart is available in [our public chart repository](https://brainboard.github.io/helm-charts/).

You will need to add the Brainboard chart repository in order to install the chart:

```bash
helm repo add brainboard https://brainboard.github.io/helm-charts/
```

### Installation

In order for the runner to enroll with your organization, you will need to provide the private self-hosted runner token you generated from the Brainboard settings page.

You can install the runner with the following command:

```bash
helm install runner brainboard/brainboard-runner --set config.credentials.token="your-runner-token"
```

You can view all available configuration options in the chart [github repository](https://github.com/brainboard/helm-charts/tree/main/charts/brainboard-runner)

#### Register runner with your organization

Once your runner is started, you will need to register it with your organization. To do so, open a terminal inside the runner container (see below) and run the following command:

```bash
/brainboard-runner register
```

This operation only needs to be done once, when the runner is started for the first time.

### Usage

To open a terminal inside the runner container, use the following command:

```bash
POD_NAME=$(kubectl get po -l app.kubernetes.io/name=brainboard-runner -o=name)
kubectl exec -ti ${POD_NAME} -c runner -- sh
```

If you want to see the logs, you can run this command:

```bash
kubectl logs -l app.kubernetes.io/name=brainboard-runner -c runner
```
