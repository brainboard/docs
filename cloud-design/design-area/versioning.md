# Versioning

### Description

Brainboard provides a native versioning mechanism that allows you to keep track of every modification you do and rollback or go to any specific point-in-time snapshot.

### Components of a version

When you create a version, Brainboard saves the following information:

* The architecture: everything in the design area.
  * The Terraform code is automatically generated predictably for any version.
* The version of the cloud provider selected to create the architecture.
* Variables.
* Output.
* The README file.
* The structure of the Terraform files.
* Timestamp in UTC when the version is created.
* The person who created the version.
* The commit message.

### Create a version

To create a version of your architecture:

1.  Click on the `Create new version` button in the options bar:&#x20;

    <figure><img src="../../.gitbook/assets/create-new-architecture-version.png" alt=""><figcaption></figcaption></figure>
2. Write a description of the version in the versioning window that will open.
3. Click on `Commit` to create the new version.

When you create a new version, if there are no changes between the current version and the new one, you'll receive this message:

![No changes message](../../.gitbook/assets/no-changes-message-versioning.png)

### Checkout a version

To checkout any version you create:

1.  Click on the `Show versions` button in the options bar:&#x20;

    <figure><img src="../../.gitbook/assets/checkout-architecture-version.png" alt=""><figcaption></figcaption></figure>
2. Click on the line of the version you want to open:

{% hint style="warning" %}


* Brainboard versions are an immutable snapshot of your infrastructure. You cannot delete them.
* You can checkout any version and work on it without altering the history of the versioning.
* When you clone an architecture or create a template from it, its versions will be cloned with it.
* When you checkout a version, both the diagram and the Terraform code will be updated.
{% endhint %}

