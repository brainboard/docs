# Configure access 🚪

### Credentials' settings

To add credentials for the supported providers you need to go to the cloud providers configuration menu where you can see the list of the supported providers.

![providers\_config](../.gitbook/assets/providers\_config.png)

There are two main configurations that are common for all terraform providers:

* `Credentials` specific credentials needed to access the cloud provider
* `Scope` the scope in Brainboard where you are going to use the provider. It might be at the organizational/project/environment/architecture level.

After selecting one of the providers, you can click on the `+` button on the right and open the configuration for the provider.

![add\_config](../.gitbook/assets/add\_config.png)

### Azure RM

To configure the Azure provider (AzureRM) for Terraform, you have to specify the appropriate credentials and the subscription in which you want to create resources.

Here are the steps to configure the Azure provider:

1. Create a service principal in Azure Active Directory (AAD) with the "Contributor" role. This service principal will be used to authenticate the Terraform Azure Provider to Azure. You can create the service principal using the Azure CLI, Azure PowerShell, or the Azure Portal.
2. Once you have the service principal created, you will need to get the following information from it:
   * **subscription\_id**
   * **client\_id**
   * **tenant\_id**
   * **client\_secret**
3. Next, you need to add the information in the AzureRM configuration below:

![azure\_config](../.gitbook/assets/azurerm\_config.png)

<details>

<summary>Generate Azure credentials for Terraform</summary>

To generate Azure credentials for use with Terraform, you can use the Azure Portal.

1. Go to the Azure portal and navigate to the Azure Active Directory section
2. Select App registrations and then click on New registration
3. Give a name to your app and select the appropriate account type (single or multi-tenant)
4. After creating the app, go to Certificates & secrets and create a new client secret
5. Go to the Subscription's Access control (IAM) to add a new role assignment
6. Assign the appropriate role (e.g. Contributor) to the app created above

Tips:

* `ARM SUBSCRIPTION ID`: you will find it in the Subscription's Overview
* `ARM CLIENT ID`: you will find it in the App registrations' Overview with the name `Application (client) ID`
* `ARM TENANT ID`: you will find it in the App registrations' Overview with the name `Directory (tenant) ID`
* `ARM CLIENT SECRET`: you will find it in the App registrations' Certificates & secrets, you must copy the client `secret Value` (not the Secret ID).

</details>

### AWS

To configure the AWS provider for Terraform, you will have to specify the name and the appropriate credentials as below :

![aws\_config](../.gitbook/assets/aws\_config.png)

<details>

<summary>Generate AWS credentials for Terraform</summary>

To generate AWS credentials for use with Terraform, you can use the AWS Management Console.

1. Log in to the AWS Management Console
2. Go to the IAM (Identity and Access Management) service
3. Select Users from the navigation menu
4. Click on the "Add user" button
5. Enter a username, select "Programmatic access" for the access type, and then click on "Next: Permissions"
6. Select "Attach existing policies directly" and then choose the appropriate permissions for the user (e.g. "AdministratorAccess" or "IAMFullAccess")
7. Click on "Next: Tags" (if desired) and then "Next: Review"
8. Click on "Create user" to create the user
9. On the "Success" page, click on the "Download .csv" button to download the credentials

</details>

### GCP

To configure the GCP (Google Cloud Platform) provider for Terraform, you will have to specify the appropriate credentials and the project in which you want to create resources.

<details>

<summary>Generate GCP credentials for Terraform</summary>

To generate GCP credentials for Terraform, you will need to create a service account in the Google Cloud Console. Here are the steps to generate GCP credentials:

1. Go to the Google Cloud Console (https://console.cloud.google.com) and select your project.
2. In the navigation menu, click on the hamburger icon (≡) and then select "IAM & admin" and then "Service accounts"
3. Click on the "Create Service Account" button.
4. In the "Create service account" form, give a name to the service account and provide a brief description.
5. Under "Role", select the role that you want to assign to the service account. This role will determine the actions that Terraform can perform with the service account.
6. Click on "Create" to create the service account.
7. Once the service account is created, you will see the option to create a key. Select "JSON" as the key type and click on "Create"
8. The JSON key file will be downloaded to your local machine. This file contains the credentials for the service account and it should be kept secure.
9. Once you have the JSON key file, you can use it to authenticate the Terraform GCP Provider to GCP.

</details>

Once you have the service account created, you will have to get the following information from it:

* project\_id
* credentials file

![gcp\_config](../.gitbook/assets/gcp\_config.png)

### OCI

To configure the Oracle Cloud Infrastructure (OCI) provider in Terraform, you will need to specify the information in the OCI configuration as below and set the appropriate variables.

![oci\_config](../.gitbook/assets/oci\_config.png)

* The tenancy\_ocid variable specifies the OCID of the tenancy that you want to use. You can find your tenancy OCID in the Oracle Cloud Infrastructure Console under the "Tenancy Information" section.
* The user\_ocid variable specifies the OCID of the user to use. You can find your user OCID in the Oracle Cloud Infrastructure Console under the "User Settings" section.
* The fingerprint variable specifies the fingerprint of the public key that you have added to your user. You can find your public key fingerprint in the Oracle Cloud Infrastructure Console under the "User Settings" section.
* The private\_key\_path variable specifies the path to the private key file that corresponds to the public key that you have added to your user. This private key will be used to sign the requests to the OCI API.

<details>

<summary>Generate OCI credentials for Terraform</summary>

To generate Oracle Cloud Infrastructure (OCI) credentials for use with Terraform, you can use the OCI Console or the OCI CLI.

1. Using OCI Console:
2. Log in to the OCI Console
3. Go to the Identity service
4. Select Users from the navigation menu
5. Click on the "Create User" button
6. Enter a username, select "Programmatic" for the access type and then click on "Create"
7. Click on the username of the user you just created
8. Click on the "Create API Key" button

Click on the "Download" button to download the private key in PEM format

</details>

### Scaleway

To configure the Scaleway provider in Terraform, you will need to specify the provider block in your Terraform configuration file and set the appropriate variables.

* Name
* Scaleway Access Key
* Scaleway Secret Key

![scaleway\_config](../.gitbook/assets/scaleway\_config.png)

To generate access and secret keys in Scaleway, you will need to create an API token in the Scaleway console.

<details>

<summary>Generate Scaleway credentials for Terraform</summary>

Here are the steps to generate access key and secret key in Scaleway:

1. Go to the Scaleway console (https://console.scaleway.com) and sign in.
2. In the navigation menu, click on "Account" and then "API Tokens"
3. Click on the "Create a token" button.
4. In the "Create an API Token" form, give a name to the token and provide a brief description.
5. Under "Rights" select the rights that you want to assign to the token. These rights will determine the actions that can be performed by the token.
6. Click on "Create" to create the token.
7. Once the token is created, you will see the option to "Show the token". This is the only time the token will be displayed.
8. Once you have the token, you can use it as an access key.
9. You can also assign or revoke rights to the token by clicking on the pencil icon next to the token.

Scaleway does not provide a secret key. Instead, it uses the token generated as the access key and no separate secret key is required.

</details>
