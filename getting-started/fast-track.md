---
icon: stopwatch
---

# Fast track

## 1. Create an account

Register [here](https://app.brainboard.co/register) to create your account. You can sign up with your Google or Microsoft login.

## 2. Create a new architecture

* Click on the `New architecture` button in the top left part.
* Select `From scratch` option.

![Create a new architecture](../.gitbook/assets/architecture-create-button.png)

## 3. Add cloud resources

Drag and drop cloud resources from the _Leftbar_ to the design area to build your architecture. Customize the cloud configuration of the resources

### Azure

![Configure the resources](../.gitbook/assets/architecture-id-card-azure.png)

### AWS

![Configure the resources](../.gitbook/assets/architecture-id-card-aws.png)

## 4. Inspect the auto-generate Terraform code

See the auto-generated Terraform code on the right pane.

### Code for Azure resource

![Terraform code Azure](../.gitbook/assets/architecture-code-generated-azure.png)

### Code for AWS resource

![Terraform code AWS](../.gitbook/assets/architecture-code-generated-aws.png)

Please refer to the support providers page to have the complete list of all supported cloud providers.

## 5. Add your cloud credentials

If you want to deploy your architecture, add your preferred cloud provider credentials [here](https://app.brainboard.co/settings/cloud-providers).

![CP creds](../.gitbook/assets/cp-creds.png)

Examples for **AWS** and **Azure**.

![AWS creds](../.gitbook/assets/aws-creds.png) ![Azure creds](../.gitbook/assets/azure-creds.png)

## 6. Trigger a plan

After adding your cloud credentials, you can trigger the Terraform / OpenTofu plan directly from the design area and get the output in real time.

<figure><img src="../.gitbook/assets/fast-track-plan-bg.png" alt=""><figcaption><p>Terraform plan action</p></figcaption></figure>

### Execution output

You see the output of the plan in the design area, in the tab next to the Terraform code:

<figure><img src="../.gitbook/assets/fast-track-plan-output-bg.png" alt=""><figcaption><p>Terraform / OpenTofu plan output</p></figcaption></figure>
