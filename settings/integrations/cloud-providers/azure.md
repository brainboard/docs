# Azure

Brainboard allows you to connect to your Azure environments, whether you want to provision resources, import existing infrastructure or simply manage your architecture on a daily basis.

It supports 2 authentication methods described below:

1. [Client certificate](azure.md#client-certificate) (recommended)
2. [Client secret](azure.md#client-secret)

{% hint style="info" %}
You need an app registration in your Azure account to be able to connect Brainboard successfully.
{% endhint %}

### Configure access

To connect Brainboard to your AWS account:

1. Go to the [Cloud providers integration](https://app.brainboard.co/settings/integrations/cloud-providers) settings page.
2. Click on `Microsoft Azure`
3.  Click on `New connection`&#x20;

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.22.18@2x.png" alt=""><figcaption></figcaption></figure>
4.  This will open the new connection page where you have 2 options:

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.22.28@2x.png" alt=""><figcaption></figcaption></figure>

### Client certificate

{% hint style="success" %}
This is the recommended way to connect to your Azure environments as it doesn't require any secret sharing.
{% endhint %}

When you click on the option `Client Certificate` Brainboard guides you in the connection process:

1.  In this page, click on `Register app` button, it will open your Azure portal with pre-filled information and download the certificate

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.40.23@2x (1).png" alt=""><figcaption></figcaption></figure>
2.  In your Azure portal, add a name of the app registration and click `Register`

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.32.27@2x.png" alt=""><figcaption></figcaption></figure>
3.  Once the app registration done, navigate to the [app registration page](https://portal.azure.com/#view/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) and search for the one you just created, then click on it to open its configuration

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.34.59@2x.png" alt=""><figcaption></figcaption></figure>
4.  Go to manage, then Certificates & secrets, and click on certificates tab and upload the certificate you downloaded in step 1

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.38.47@2x.png" alt=""><figcaption></figcaption></figure>
5. In the same app registration page, click on overview to get the follow information:
   1. Application (client) id
   2. Directory (tenant) id
6. Go to the subscription that you want to connect to Brainboard and get its ID
7.  Navigate to Access control (IAM) to create a role assignment with the right privilege

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.47.58@2x.png" alt=""><figcaption></figcaption></figure>
8. In Brainboard, put all the information you collected before, and click `Continue`:
   1. Application (client) id
   2. Directory (tenant) id
   3. Subscription id
9. Brainboard checks if the connection can be established:
   1.  If the connection is successful, you will have this message

       <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.51.09@2x.png" alt=""><figcaption></figcaption></figure>
   2.  If it fails, you get an information about it

       <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.52.48@2x.png" alt=""><figcaption></figcaption></figure>
10. Name the connection in Brainboard

    <figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.52.13@2x.png" alt=""><figcaption></figcaption></figure>

    This name is used only within Brainboard, so it's a best practice to give an explicit name that allows you to identify which subscription is referring to.

### Client secret

Brainboard allows you to add your client secret if this is your preferred way to connect to your Azure environments:

<figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.56.54@2x.png" alt=""><figcaption></figcaption></figure>

Follow the same steps as [#client-certificate](azure.md#client-certificate "mention") except in step 4, generate a new client secret

<figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 16.59.07@2x.png" alt=""><figcaption></figcaption></figure>

### Set the scope

Once your credentials are added you can specify where exactly they will be used

<figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 17.02.49@2x.png" alt=""><figcaption></figcaption></figure>

This allows you to specify whether you want:

1. Make the credentials the default to use within your organization: which means any architecture created in Brainboard will use these credentials if it doesn't have its own ones.
2. Use in a specific project
3. Use in a specific environment
4. Use in a specific architecture

<figure><img src="../../../.gitbook/assets/CleanShot 2025-04-24 at 17.03.39@2x (1).png" alt=""><figcaption></figcaption></figure>
