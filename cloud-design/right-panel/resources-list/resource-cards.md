# Resource Cards

## Card Components

Each resource card displays:

1. **Resource Icon:** Visual indicator of the resource type (e.g., storage account, virtual machine, function app).
2. **Resource Name:** The <mark style="color:$primary;">Terraform</mark> resource name you've assigned.
3. **Resource Type:** The <mark style="color:$primary;">Terraform</mark> resource type (e.g., `azurerm_storage_account`, `aws_s3_bucket`)
4. **Key Parameters:** Most important configuration values:
   * Required parameters.
   * Connection references to other resources.
   * Location/region information.
   * Names and identifiers.
5. **File Assignment:** Shows which <mark style="color:$primary;">Terraform</mark> file contains this resource.

***

## Parameter Display

Parameters are displayed in different formats based on their type:

* **Simple Values:** Strings and numbers shown directly (e.g., `"Standard"`, `"LRS"`)
* **References:** Links to other resources shown with an icon and resource name (e.g., `→ resource_group.name`)
* **Variables:** Variable references shown with variable icon (e.g., `var.location`).
* **Complex Objects:** Nested configuration indicated with a message: "View full configuration in the Resource Configurator".

{% hint style="info" %}
Parameter references are clickable - click any reference to navigate to the referenced `resource`, `variable`, or `output`.
{% endhint %}

#### **Viewing parameters**

Hover over any parameter value to see:

* Parameter documentation.
* Data type information.
* Default values.
* Validation requirements.

***

## Resource Relationship Indicators

Resource cards show relationship indicators:

* **Incoming References:** Icon shows when other resources reference this one.
* **Outgoing References:** Displayed as clickable parameter values.
* **Module Connections:** Special indicator for module-sourced resources.

***

## Card Actions

Each resource card provides quick actions:

* **Click Resource Card:** It highlights the corresponding resource in the architecture diagram. IT is useful for large diagrams where resources may be off-screen.
* **Double-Click:** Double-clicking a resource card opens the [Resource Configuration](../../resource-configuration.md) panel for detailed editing. Or, you can also right-click on the resource card and select **"Edit Config"** from the actions menu.
* **Minimize/Expand:** Toggle between collapsed and expanded parameter view.
* **Actions Menu** (⋯): Access additional options:
  * Configure resource
  * Switch to data source/resource
  * Terraform state (import resource)
  * Duplicate
  * Delete
