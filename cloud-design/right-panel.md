---
description: >-
  This article covers the information about the options/features available in
  the right panel, right panel controls, and best practices. You can also find
  links to the related articles at the end.
icon: sidebar-flip
---

# Right Panel

## Overview

The **Right Panel** in Brainboard provides quick access to your architecture's resources, generated code, validation issues, and deployment configuration. It serves as a central hub for reviewing, configuring, and managing your cloud infrastructure.

***

## Available tabs

The Right Panel features four main tabs, each serving a specific purpose:

1. **Resources:** View and manage all resources in your architecture.
2. **Code:** View and edit generated Terraform code.
3. **Issues:** Review architecture warnings and validation errors.
4. **Deploy:** Configure and monitor CI/CD deployment pipelines.

### 1. Resources

The **Resources** tab displays all cloud resources in your current architecture, providing a card-based interface for quick navigation and configuration.

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

#### Key Features

* **Resource Cards:** Each resource is displayed as a card showing:
  * Resource icon and name.
  * Resource type and provider.
  * Key configuration parameters.
  * Reference relationships to other resources.
* **Search:** Filter resources by name, type, or properties.
* **Quick Actions:** Access common actions directly from resource cards:
  * Double-click to open the [Resource Configuration](resource-configuration.md) panel for detailed editing.
  * View parameter values and references.
  * Navigate to connected resources.

{% hint style="info" %}
Resources displayed in the right panel reflect the current state of your visual diagram. Changes made visually are immediately reflected in the right panel.
{% endhint %}

#### View Modes

The **Resources** tab supports two view modes:&#x20;

* **Dynamic View:** All resources displayed in a single scrollable list.
* **Group by file:** Resources are organized by their Terraform file assignment.

{% hint style="info" %}
You can switch between these modes by using the gear wheel settings icon ⚙️ and selecting <mark style="color:$primary;">**Group by File**</mark> / <mark style="color:$primary;">**Dynamic View**</mark>.&#x20;

By default, the resources are listed in the **Dynamic View.**&#x20;
{% endhint %}

{% hint style="info" %}
Learn more about managing resources in the [Resources List](resources-list.md).
{% endhint %}

***

### 2. Code

The **Code** tab provides direct access to view and edit your auto-generated **Terraform** code. This feature is ideal for users who prefer code-centric workflows or need to make quick adjustments.

#### Key Features

* **File Selector:** Switch between different **Terraform** files _<mark style="color:$primary;">(main.tf, variables.tf, outputs.tf, etc.).</mark>_
* **Syntax Highlighting:** Full Terraform HCL syntax support.
* **Code Validation:** Real-time validation with error reporting.
* **Keyboard Shortcuts**:
  * `CMD/CTRL+S` - Save changes.
  * `CMD/CTRL+F` - Search.
  * `CMD/CTRL+H` - Find and replace.
  * `CMD/CTRL+SHIFT+R` - Discard changes.

{% hint style="warning" %}
Changes made in the code editor are bidirectional - they update both the code and the visual diagram. However, some limitations apply to preserve Brainboard's structured approach.
{% endhint %}

{% hint style="info" %}
Learn more about code editing in [Code Edition](code-edition.md).
{% endhint %}

***

### 3. Issues

The **Issues** tab displays architecture warnings and validation errors, helping you maintain best practices and catch configuration problems early.

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

#### Key Features

* **Architecture Warnings:** Identifies potential configuration issues:
  * Missing required parameters.
  * Unconnected resources.
  * Security best practice violations.
  * Resource relationship inconsistencies.
* **Validation Errors:** Shows Terraform validation errors before deployment.
* **Quick Navigation:** Click any issue to navigate to the affected resource.

{% hint style="info" %}
Regular review of the **Issues** tab helps maintain infrastructure quality and prevents deployment failures.
{% endhint %}

***

### 4. Deploy

The **Deploy** tab provides access to Brainboard's deployment pipeline configuration and monitoring capabilities.

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

#### Key Features

* **Pipeline Configuration:** Set up and manage deployment workflows.
* **Environment Settings:** Configure deployment targets.
* **Execution History:** View past deployment runs and their status.
* **Quick Actions:** Trigger deployments directly from the panel

{% hint style="info" %}
Learn more about deployment in [CI/CD Designer](../automation/ci-cd-designer.md) and [Pipelines](../automation/pipelines.md).
{% endhint %}

***

## Panel Controls

### Collapsing/expanding the Panel

Click the **arrow icon** at the top of the panel to collapse/expand it.

<figure><img src="../.gitbook/assets/image (62).png" alt="" width="511"><figcaption></figcaption></figure>

### Keyboard Shortcuts

* `SHIFT+CMD+D` / `SHIFT+CTRL+D` - Toggle **Code** tab.
* `SHIFT+CMD+R` / `SHIFT+CTRL+R` - Toggle **Resources** tab.

### Resizing

Drag the **left edge** of the panel to resize its width according to your preference.

***

## Best Practices

* **Use the&#x20;**<mark style="color:$primary;">**Resources**</mark>**&#x20;tab** for quick parameter checks and navigation between resources.
* **Use the&#x20;**<mark style="color:$primary;">**Code**</mark>**&#x20;tab** when you need to make bulk changes or prefer code-first workflows.
* **Check the&#x20;**<mark style="color:$primary;">**Issues**</mark>**&#x20;tab** regularly, especially before running Terraform plan or apply.
* **Configure the&#x20;**<mark style="color:$primary;">**Deploy**</mark>**&#x20;tab** once and use it to maintain consistent deployment workflows.

***

## Related articles

* [Resources List](resources-list.md): Detailed resource management.
* [Resource Configuration](resource-configuration.md): Advanced resource configuration.
* [Code Edition](code-edition.md): Code editing capabilities.
* [Design Area](design-area/): Visual diagram interface.
