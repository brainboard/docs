# Import from AWS

### Description

Brainboard allows you to import your cloud infrastructure from AWS, and will generate the architecture diagram, the Terraform code and the tfstate for you.

{% hint style="info" %}
This is considered a migration to Brainboard and not intended to be used a remediation to the drift.

Please check [drift](../../automation/drift/ "mention")section to understand how it works and how you can setup a remediation.
{% endhint %}

### Import from AWS provider prerequisites

When importing resources from AWS provider, Brainboard will scan your cloud account resources using the following AWS services:

* [AWS Resource Groups Tagging](https://docs.aws.amazon.com/resourcegroupstagging/latest/APIReference/overview.html): this service will list any resource which has been tagged at least once
* [AWS resource explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/welcome.html): this service will list all resources matching Resource Explorer view index.

Brainboard will scan your cloud account using the best effort method: it will try to find as many resources as possible, using AWS resource explorer in priority if possible.

#### Create indexes

In order for AWS Resource Explorer to list your existing resources, AWS needs to frequently update its search index.

The index is based per region, so we recommend creating indexes for all your regions and then selecting your main region as an **aggregator index**. An aggregator index will aggregate results from all other regions indexes.

If you haven't already created indexes, here are the steps to take:

1. Open the [AWS Resource Explorer console](https://console.aws.amazon.com/resource-explorer/home)
2. Navigate to the `Settings` menu in the left panel:

![AWS resource explorer settings menu](../../.gitbook/assets/aws-resource-explorer-settings-menu.png)

3. Click on `Create Indexes`:

![AWS resource explorer create index](../../.gitbook/assets/aws-resource-explorer-settings-create-index.png)

4. Select all regions and click on `Create Indexes`:

![AWS resource explorer new index](../../.gitbook/assets/aws-resource-explorer-settings-new-index.png)

5. Go back to the `Settings` menu, select your aggregator region and click on `Change Index Type`:

![AWS resource explorer select aggregator index](../../.gitbook/assets/aws-resource-explorer-settings-select-aggregator-index.png)

6. In the modal window, select `Aggregator Index` and click on `Save changes`:

![AWS resource explorer set aggregator index](../../.gitbook/assets/aws-resource-explorer-settings-set-aggregator-index.png)

#### Create a default view

When using Resource Explorer service, Brainboard will look for a **default view** in one of the regions you select during the import steps.

Here are the steps to create a default view in AWS Resource Explorer:

1. Open the [AWS Resource Explorer console](https://console.aws.amazon.com/resource-explorer/home)
2. Navigate to the `Views` menu in the left panel:

![AWS resource explorer view menu](../../.gitbook/assets/aws-resource-explorer-views-menu.png)

3. Click on `Create View`:

![AWS resource explorer create view button](../../.gitbook/assets/aws-resource-explorer-views-create-button.png)

4. In the view creation form, set a name for your view and **make sure you select the region containing the aggregator index** you created in the previous step:

![AWS resource explorer create view form](../../.gitbook/assets/aws-resource-explorer-views-create-form.png)

5. Once the view has been created, select the view and click on Actions button to set this view as default view:

![AWS resource explorer set default view](../../.gitbook/assets/aws-resource-explorer-views-set-default.png)

### Import cloud resources

Once your account is correctly configured to list cloud resources, you can import them into a new Brainboard architecture.

1. Click on new architecture button in the top left corner
2. Select the `import from your infrastructure` option:

![Create architecture import data](<../../.gitbook/assets/CleanShot 2025-05-23 at 19.04.37@2x (1).png>)

3. Select the `From you Cloud providers` option:

![Create architecture cloud provider option](<../../.gitbook/assets/CleanShot 2025-05-23 at 19.07.14@2x.png>)

4. Select AWS

<figure><img src="../../.gitbook/assets/CleanShot 2025-05-23 at 19.08.25@2x.png" alt=""><figcaption></figcaption></figure>

5. Select the credentials / the account that you want to import from

<figure><img src="../../.gitbook/assets/CleanShot 2025-05-23 at 19.10.51@2x.png" alt=""><figcaption></figcaption></figure>

6. The next pages explain the mechanism to use to import your infrastructure. Please read them to know which way is best for you and click Next

<figure><img src="../../.gitbook/assets/CleanShot 2025-05-23 at 19.12.23@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/CleanShot 2025-05-23 at 19.12.34@2x (1).png" alt=""><figcaption></figcaption></figure>

7. Select the region(s) of your infrastructure

<figure><img src="../../.gitbook/assets/CleanShot 2025-05-23 at 19.12.52@2x.png" alt=""><figcaption></figcaption></figure>

8. Brainboard scans your region(s) and list all the resources for you that you can filter exactly those you want to import

<figure><img src="../../.gitbook/assets/CleanShot 2025-05-23 at 19.17.09@2x.png" alt=""><figcaption></figcaption></figure>

9. Give a name to your architecture and click on `Start import`&#x20;

<figure><img src="../../.gitbook/assets/CleanShot 2025-05-23 at 19.17.48@2x.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Importing resources from your cloud account can take a long time, depending on the number of resources Brainboard will find in your account. You can either keep the import window open or wait for an email notification once the import is complete.&#x20;

You will also be notified in the app when the import is done.
{% endhint %}

This window will also display the remaining import credits in your Brainboard account.

Every time you select a resource to import, the number of credits that will be deducted from your account displayed at the bottom of the window is refreshed.
