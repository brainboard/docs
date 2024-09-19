---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Cloud resources

### Description

The cloud resource is the building block of any architecture in Brainboard and could be:

1. Any resource available at the cloud provider that has either a Terraform resource or data source associated with it.
2. Terraform module.
3. Brainboard reference object that doesn't have a Terraform equivalent resource but helps you build accurate architecture and generate a correct Terraform code. For e.g. containers like Azure location, AWS region.

Characteristics of a cloud resource:

* It can be drag & dropped from the left bar.
* It has a lifecycle associated to it, so it can be created, updated and deleted.
* It has a set of configuration parameters that you can customize through the ID card.
  * Refer to the [identity card](../../cloud-architectures/id-card.md) page for more information on how to configure a cloud resource.

### Types of cloud resources

Brainboard supports all the Terraform/OpenTofu resource types and you have the possibility to switch between the data types and resources in 2 ways:

1.  **From the left bar:** Select either a resource or data source option as follows:

    ![](../../.gitbook/assets/leftbar-resource-option.png)![](../../.gitbook/assets/leftbar-data-resource-option.png)
2.  **Inside the design area:** If you want to switch any resource in to data or vice-versa, right click on the resource and select either `Switch to data` or `Switch to resource.`

    ![](../../.gitbook/assets/node-context-menu-switch-to-resource.png)![](../../.gitbook/assets/node-context-menu-switch-to-data.png)

{% hint style="info" %}
When you switch a resource into data, Brainboard automatically changes all the references of this resource in the Terraform code into a data block and also updates the configuration of its ID card.
{% endhint %}

#### Resources:

They represent, for a specific cloud provider, all the resources available at any selected version of the Terraform provider.

#### Data sources:

Data sources allow you to reference existing resources and access their information in a read-only mode.

**Agnostic nodes**

Nodes like Texts, generic icons or graphical shapes have no cloud configuration and will not be deployed into any cloud provider. They are diagraming objects only to help you represent information that cannot be represented by code.

* You can convert any cloud resource into an icon, which also removes its Terraform code by right-clicking on the resource and choose the option `Omit from code`.

<figure><img src="../../.gitbook/assets/node-context-menu-omit-from-code.png" alt=""><figcaption></figcaption></figure>

* You can change it back into a cloud resource. Its original configuration will be restored and its Terraform code will be shown as well.

<figure><img src="../../.gitbook/assets/node-context-menu-add-to-code.png" alt=""><figcaption></figcaption></figure>

Refer to the Node documentation page to understand what visual indications mean and to understand how cloud resources behave in the design area.

#### Terraform modules

These are a special cloud resources as they are containers and abstract a group of cloud resources.

Brainboard support any type of Terraform modules from any source.

Here is the section in the left bar where you can import your modules and access the modules' catalog to manage them.

<figure><img src="../../.gitbook/assets/leftbar-modules-section.png" alt=""><figcaption></figcaption></figure>









Refer to the Node documentation page to understand what visual indications mean and to understand how modules behave in the design area.

### Terraform code

When you add a resource into the design area, Brainboard generates its Terraform code instantly and automatically, and highlights it in the embedded VS Code editor.

When you click on any resource, Brainboard highlights it in the code and vice versa, when you click on the name of the resource in the code, Brainboard automatically selects the resource and opens its configuration menu.

### Best practices

* Always start by adding containers first into the design, this way Brainboard will detect automatically any resource you insert inside them, whatever the number of layers.
* If you want to stay compliant with Terraform, always put the Terraform resource name you choose as a text of the resource as well.
* Use the native auto-inheritance mechanism of Brainboard when you add resources. It saves you a lot of time.
