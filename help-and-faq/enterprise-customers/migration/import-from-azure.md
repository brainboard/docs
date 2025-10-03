# Import from Azure

### Description

Brainboard allows you to import your cloud infrastructure from Azure, and will generate the architecture diagram, the Terraform code and the tfstate for you.

{% hint style="info" %}
This is considered a migration to Brainboard and it is not intended to be used a remediation to the drift.

Please check [drift](../../../automation/drift/ "mention")section to understand how it works and how you can setup a remediation.
{% endhint %}

### Import from Azure provider prerequisites

When importing resources from Azure provider, Brainboard will scan your cloud account resources using Azure API with the permissions assigned to the credentials you use.

The only requirement to import from Azure is to add your credentials with the right permissions.

Please refer to the [azure.md](../../../settings/integrations/cloud-providers/azure.md "mention")page to know how to connect Brainboard to your Azure environment.

{% hint style="info" %}
* ReadOnly is enough if you want to only import the resources. If you are planning to manage the infrastructure with Brainboard after the import, you need a Contributor role.
{% endhint %}

### Import cloud resources

The import process has 3 phases:

1. **Resources listing:**
   1.  Click on `New architecture` button in the top left and select `Import from your infrastructure` option:\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-10 at 15.35.53@2x.png" alt=""><figcaption></figcaption></figure>
   2.  Select the option `From your Cloud provider` as the source of the import:\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-10 at 15.37.29@2x.png" alt=""><figcaption></figcaption></figure>
   3.  Select `Azure` option\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-10 at 15.39.07@2x.png" alt=""><figcaption></figcaption></figure>
   4.  Select the right credentials / subscription where you want to import the resources from\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 08.58.23@2x.png" alt=""><figcaption></figcaption></figure>
   5.  Brainboard will scan the subscription to list `all` the resource groups visible. You select the one(s) you want to import\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 08.59.46@2x.png" alt=""><figcaption></figcaption></figure>
   6.  Brainboard will list `all` the resources inside the resource group(s) you've selected.\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 09.04.18@2x.png" alt=""><figcaption></figcaption></figure>

       This operation will take a few minutes to complete, depending on the number of the resource groups you selected and the number of the resources inside them.

       1. The table of the resources once available for selection
       2.  The number of credits you have for the import.

           1 credit = 1 Terraform resource generated.
2. **Filtering and selection**
   1.  Filter and select the resources to import. This table is optimized to help you filter based on different criteria and select exactly what you need:\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 09.08.12@2x.png" alt=""><figcaption></figcaption></figure>

       Here are the different options you have:

       1.  Powerful search bar that will search across all fields but you can also target a specific field by typing the name of the column followed by `>>`. For e.g, if you want to search for a specific tag:\


           <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 09.12.31@2x.png" alt=""><figcaption></figcaption></figure>
       2.  The `Type` filter allows you to display only the Azure service you want to import. Here is how it looks like if you want to only select Key vault from the list:\


           <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 09.14.59@2x.png" alt=""><figcaption></figcaption></figure>
       3. The `Resource group` filter allows you to only select the resources of the RGs you are interested in. This is applicable when you have more than 1 RG.
       4.  With the `View` button, you can show/hide columns from the table\


           <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 09.18.18@2x.png" alt=""><figcaption></figcaption></figure>
       5. The `Refresh` button will trigger a complete scanning of your subscription to generate a new list. This is useful in case there are changes (new resources created, for e.g), between the scan and this listing.
       6. The table contains all the resources filtered and selected by on your criteria and ready to be imported
3. **Import**
   1.  Give a name to your architecture and click `Start import`, the process starts:\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 09.34.38@2x.png" alt=""><figcaption></figcaption></figure>

       * This operation may take a few minutes or hours based on the number of the resource groups you select and the number of the resources inside them.
       * Once the process is finished you, you'll receive a notification in the app (in the top-right corner) and an email with the link to the import. Here are samples:\
         ![](<../../../.gitbook/assets/CleanShot 2025-06-12 at 09.34.49@2x.png>)![](<../../../.gitbook/assets/CleanShot 2025-06-12 at 09.39.13@2x.png>)
   2.  If the import is successful, you will see the diagram of your infrastructure, the Terraform code and the tfstate\


       <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 10.19.05@2x.png" alt=""><figcaption></figcaption></figure>



### Azure permissions

In Azure, to be able to import all your resources, sometimes granting `Read` permission on the top level resource is not enough. You need to grant access to the underlying sub-resources. For e.g. to access key vault keys, you need to explicitly grant read permission on the keys even if you already have a read permission on the key vault itself.

Here is a list of the permissions you need to import your resources, that you can use to create a custom role. If you still face a permission issue on resources or permissions not listed here, you need to add them into the role.

{% file src="../../../.gitbook/assets/Brainboard Azure Import.json" %}

### Limitations

When you import your cloud infrastructure, here is what you need to know about what is imported and how:

* The import uses Azure API, so all the resources available through the API are supported
* Information that are not disclosed by Azure are not available, for e.g:
  * Virtual machine passwords
  * Database passwords
  * Sensitive information

{% hint style="info" %}
So we replace these sensitive information in the code with a placeholder string "_ignored-as-imported_"
{% endhint %}

* The goal is to run the plan without having any errors, but sometimes you may have some:
  * When only one parameter is needed out of 2 possible. When we do the import, the default values are imported from Azure. So even if we are continuously improving the process to fix this mutually exclusive parameters, in some situations we keep it as it is for the user to decide what is correct.

### Best practices

* Do smaller imports: The golden rule is to import only resources that are supposed to be managed in the same lifecycle:
  * To reduce the blast radius
  * Have a light tfstate for future operations
  * Better diagram and code navigation
* If you have different environments like dev, staging and prod, don't import them all in one import. Separate the environments and do different imports for different purposes.
* Don't import sensitive information in clear text. Surprisingly, when you do the import, if the credentials are allowed to read the key vault secrets it will be able to list them for import. Better to not import them and just reference them using the `data objects` instead.
*   After the first import, create a version in Brainboard called for e.g, `Initial import` . This is an immutable snapshot that you can revert to if needed later.\


    <figure><img src="../../../.gitbook/assets/CleanShot 2025-06-12 at 10.36.57@2x.png" alt=""><figcaption></figcaption></figure>

