# Supported cloud providers 🎩

### Cloud provider definition

A **Terraform cloud provider** is a plugin that allows Terraform to interact with a specific cloud provider's API to create, manage, and delete resources. Each cloud provider has its own set of resources and data sources that can be used to define and manage infrastructure with Terraform.

You can use the provider block to specify which cloud provider you are using and configure its settings.

{% hint style="info" %}
This block is typically placed at the top of a Terraform configuration file, and you can specify multiple providers to manage resources across multiple cloud providers
{% endhint %}

### Supported cloud providers

Brainboard supports the following cloud providers:

#### Azure (Azure Resource Manager)

`AzureRM` is the Terraform provider for Azure Resource Manager (ARM), which is the service that allows you to manage Azure resources.

* It provides Terraform with the necessary API calls to interact with Azure's API and create, manage, and delete resources within your Azure account.
* When you use the AzureRM provider in Terraform, you can define resources such as virtual machines, storage accounts, and virtual networks, and use Terraform to create, update, and delete those resources in Azure.

{% hint style="info" %}
To use the Azure provider in Terraform, you need to configure it with the appropriate credentials and specify which Azure subscription and resource group you want to use.

Refer to the [credential page](./) to understand how to do it
{% endhint %}

#### AWS (Amazon Web Services)

The `AWS` provider for Terraform is a plugin that allows Terraform to interact with the AWS API to create, manage, and delete resources within an AWS account.

* It provides Terraform with the necessary API calls to create, update, and delete AWS resources such as EC2 instances, S3 buckets, and RDS databases.

{% hint style="info" %}
The provider needs to be configured with AWS credentials (access key and secret key) and a region.

Refer to the [credential page](./) to understand how to do it
{% endhint %}

#### Oracle or OCI (Oracle Cloud Infrastructure)

`Oracle Cloud Infrastructure` provider is a plugin that allows Terraform to interact with the Oracle Cloud Infrastructure (OCI) API to create, manage, and delete resources within an OCI account.

* It provides Terraform with the necessary API calls to create, update, and delete OCI resources such as Compute instances, Virtual Cloud Networks, and Block Volumes. It also allows managing other resources that are not directly related to OCI, such as DNS records, and others.

{% hint style="info" %}
To use the OCI provider in Terraform, you will need to configure it with the appropriate credentials and specify which OCI Tenancy and compartment you want to use.

The provider needs to be configured with the OCI configuration file and the appropriate user's API key and Tenancy OCID.

Refer to the [credential page](./) to understand how to do it
{% endhint %}

#### GCP (Google Cloud Platform)

`Google Cloud Platform` provider for Terraform is a plugin that allows Terraform to interact with the Google Cloud API to create, manage, and delete resources within a GCP project.

* It provides Terraform with the necessary API calls to create, update, and delete GCP resources such as Compute Engine instances, Cloud Storage buckets, and Cloud SQL databases.

{% hint style="info" %}
To use the GCP provider in Terraform, you will need to configure it with the appropriate credentials, such as a service account key, and specify which GCP project to use.

Refer to the [credential page](./) to understand how to do it
{% endhint %}

#### Scaleway

`Scaleway` provider for Terraform is a plugin that allows Terraform to interact with the Scaleway API to create, manage, and delete resources within a Scaleway account.

* It provides Terraform with the necessary API calls to create, update, and delete Scaleway resources such as Compute instances, Volumes, and Networks.

{% hint style="info" %}
To use the Scaleway provider in Terraform, you will need to configure it with the appropriate credentials, such as an API key, and specify which Scaleway organization you want to use.

Refer to the [credential page](./) to understand how to do it
{% endhint %}

### Providers versions

Every Terraform cloud provider has different versions for both its resources and data sources.

You can select any version from the list of versions:

![CP versions](../.gitbook/assets/cp-versions-list.png)

When you select a specific version, Brainboard loads all the resources of this version and the id-card of every resource will contain the parameters available in the selected version.

{% hint style="warning" %}
When selecting a different version, always do a `plan` to make sure that the code is valid, as most often parameters are updated between versions and some resources may be added or deleted
{% endhint %}
