---
icon: house-lock
---

# Self-Hosted Runner

{% hint style="warning" icon="info" %}
This feature is available in the **Enterprise Plan** only.
{% endhint %}

### Overview

<mark style="color:$primary;">**Brainboard**</mark>**&#x20;Runner** is a service that runs all **CI/CD** jobs in your organisation and sends the results back to <mark style="color:$primary;">**Brainboard**</mark>. A **self-hosted runner** allows you to run your pipeline jobs in your own infrastructure.

A self-hosted runner created is <mark style="color:blue;">**global**</mark> to your organization and will therefore process all jobs created within your organization, regardless of which project's architecture the jobs belong to, or which user created the job.

One organization can have multiple self-hosted runners, but these runners cannot be shared across multiple organizations.

{% hint style="success" %}
You can use **self-hosted runners** to run jobs in a **private network** or to customize the hardware and software configuration of the machines that run your jobs.
{% endhint %}

{% hint style="info" %}
<mark style="color:$primary;">**Brainboard**</mark> self-hosted runner will need to be able to communicate with the <mark style="color:$primary;">**Brainboard**</mark>**&#x20;API** to get job information and send the results, so your network needs to allow outbound traffic to the Brainboard API in order for the runner to communicate with Brainboard.

However, you do not need any specific ingress rule, because the <mark style="color:$primary;">**Brainboard**</mark>**&#x20;API** does not communicate with the runner.
{% endhint %}

### Generate runner token

To use the **self-hosted runner**, you first have to generate a **runner token** from the <mark style="color:$primary;">**Brainboard**</mark> web application. To get the runner token, you have to be logged in with an account having organization's <mark style="color:$primary;">**`Admin`**</mark> or <mark style="color:$primary;">**`Owner`**</mark> permissions.

To generate the runner token:

1. Go to the [private self-hosted runner](https://app.brainboard.co/settings/integrations/private-selfhosted-runner?) settings page. On this page, you can create a new runner token or revoke an existing one.
2. Click on the <mark style="color:$primary;">**`New runner token`**</mark> button.
3. Click the <mark style="color:$primary;">**`Generate runner token`**</mark> button. &#x20;
4. **Copy** the generated token and save it for the deployment step.

<figure><img src="../../.gitbook/assets/self-hosted-token (1).png" alt=""><figcaption></figcaption></figure>

### Deploy self-hosted runner

You can deploy the self-hosted runner in your environment using two methods:&#x20;

1. Docker-compose
2. Kubernetes

<table data-view="cards"><thead><tr><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td>Deploy runner with docker-compose [Easy]</td><td><a href="runner-docker-compose.md">runner-docker-compose.md</a></td><td><a href="../../.gitbook/assets/docker-compose.jpg">docker-compose.jpg</a></td></tr><tr><td>Deploy runner with Kubernetes [Advanced]</td><td><a href="runner-kubernetes.md">runner-kubernetes.md</a></td><td><a href="../../.gitbook/assets/Kubernetes-Logo-2048x1152.png">Kubernetes-Logo-2048x1152.png</a></td></tr></tbody></table>
