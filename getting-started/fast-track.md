---
icon: stopwatch
---

# Fast track

### 1. Create an account

Register [here](https://app.brainboard.co/register) to create your account. You can sign up with your Google or Microsoft login.

### 2. Create a new architecture

* Click on the <mark style="color:$primary;">**`New architecture`**</mark> button in the top left part.
* Select <mark style="color:$primary;">**`From scratch`**</mark> option.

<figure><img src="../.gitbook/assets/New-architecture.png" alt=""><figcaption></figcaption></figure>

### 3. Add cloud resources

Drag and drop cloud resources from the _**left bar**_ to the design area to build your architecture. Customize the cloud configuration of the resources

#### Azure

<figure><img src="../.gitbook/assets/add-cloud-resources.png" alt=""><figcaption></figcaption></figure>

#### AWS

<figure><img src="../.gitbook/assets/AWS.png" alt=""><figcaption></figcaption></figure>

### 4. Inspect the auto-generated Terraform code

See the auto-generated **Terraform** code in the right pane.

Code for Azure & AWS resources:

<div><figure><img src="../.gitbook/assets/Azure-r.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/AWS-code.png" alt=""><figcaption></figcaption></figure></div>

Please refer to the support providers page to have the complete list of all supported cloud providers.

### 5. Add your cloud credentials

If you want to deploy your architecture, add your preferred cloud provider credentials [here](https://app.brainboard.co/settings/integrations/cloud-providers).

<figure><img src="../.gitbook/assets/fast-track-cloud-providers.png" alt=""><figcaption><p>Cloud credentials</p></figcaption></figure>

Example for **Azure** credentials.

<figure><img src="../.gitbook/assets/Azure-config.png" alt=""><figcaption></figcaption></figure>

### 6. Trigger a plan

After adding your cloud credentials, you can trigger the **Terraform / OpenTofu** plan directly from the design area and get the output in real time.

<figure><img src="../.gitbook/assets/Trigger-plan.png" alt=""><figcaption></figcaption></figure>

#### Execution output

The output of the plan execution becomes available in the <mark style="color:$primary;">**`Deployment`**</mark> tab in the right panel.&#x20;

<figure><img src="../.gitbook/assets/execution-output-new (1).png" alt=""><figcaption></figcaption></figure>
