# Deploy runner with Kubernetes

{% hint style="warning" icon="info" %}
**Feature Availability: Self-Hosted Runner** is available in the **Enterprise Plan** only.
{% endhint %}

### Pre-requisites

* A running **Kubernetes cluster**
* [Helm](https://helm.sh/docs/intro/install) installed locally
* **Kubectl** installed locally

<mark style="color:$primary;">**Brainboard**</mark> provides a **Helm** chart to deploy the runner in your existing **Kubernetes cluster.**

{% hint style="info" %}
Please contact support to get your customer token (<mark style="color:blue;">**`CUSTOMER_TOKEN`**</mark>) to access the charts.
{% endhint %}

```shell
helm registry login ghcr.io --username brainboard --password $CUSTOMER_TOKEN
```

To see the charts values and documentation, you can use the following commands:

```bash
helm show values oci://ghcr.io/brainboard/helm/brainboard-runner
helm show readme oci://ghcr.io/brainboard/helm/brainboard-runner
```

### Installation

For the runner to enrol with your organization, you will need to provide the **private self-hosted runner** token you generated from the <mark style="color:$primary;">**Brainboard**</mark> settings page.

You can install the runner with the following command:

```bash
helm install runner oci://ghcr.io/brainboard/helm/brainboard-runner --set config.credentials.token="your-runner-token"
```

{% hint style="success" %}
You can **view** all available configuration options using the commands above.
{% endhint %}

### Usage

To **open a terminal** inside the runner container, use the following command:

```bash
POD_NAME=$(kubectl get po -l app.kubernetes.io/name=brainboard-runner -o=name)
kubectl exec -ti ${POD_NAME} -c runner -- sh
```

If you want to see the logs, you can run this command:

```bash
kubectl logs -l app.kubernetes.io/name=brainboard-runner -c runner
```
