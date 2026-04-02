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

## Panel Controls

### Collapsing/expanding the Panel

Click the **arrow icon** at the top of the panel to collapse/expand it.

<figure><img src="../.gitbook/assets/image (62).png" alt="" width="511"><figcaption></figcaption></figure>

### Keyboard Shortcuts

* `SHIFT+CMD+D` / `SHIFT+CTRL+D` - Toggle **Code** tab.
* `SHIFT+CMD+R` / `SHIFT+CTRL+R` - Toggle **Resources** tab.

### Resizing

Drag the **left edge** of the panel to resize its width according to your preference.

## Available tabs

The Right Panel features four main tabs, each serving a specific purpose:

1. [**Resources**](/broken/pages/ew4sNtDnTiwht6exaLMs)**:** View and manage all resources in your architecture.
2. [**Code**](right-panel/code.md)**:** View and edit generated Terraform code.
3. [**Issues**](right-panel/issues.md)**:** Review architecture warnings and validation errors.
4. [**Deploy**](right-panel/deploy.md)**:** Configure and monitor CI/CD deployment pipelines.

## Best Practices

* **Use the&#x20;**<mark style="color:$primary;">**Resources**</mark>**&#x20;tab** for quick parameter checks and navigation between resources.
* **Use the&#x20;**<mark style="color:$primary;">**Code**</mark>**&#x20;tab** when you need to make bulk changes or prefer code-first workflows.
* **Check the&#x20;**<mark style="color:$primary;">**Issues**</mark>**&#x20;tab** regularly, especially before running Terraform plan or apply.
* **Configure the&#x20;**<mark style="color:$primary;">**Deploy**</mark>**&#x20;tab** once and use it to maintain consistent deployment workflows.

***

## Related articles

* [Resources List](right-panel/resources-list/): Detailed resource management.
* [Resource Configuration](resource-configuration.md): Advanced resource configuration.
* [Code Edition](code-edition.md): Code editing capabilities.
* [Design Area](design-area/): Visual diagram interface.
