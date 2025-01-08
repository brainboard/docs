# Checkov

This plugin allows you to scan you Terraform code to find misconfigurations before they're deployed.

* [Home page](https://www.checkov.io/).
* [Source code on Github](https://github.com/bridgecrewio/checkov).

![Checkov plugin](../../../.gitbook/assets/checkov-plugin.png)

**Configuration options**

1. Version: always points to the latest version.
2. BC API key.
3. Checks.
4. Custom arguments.
5. Ignore failure: if enabled, the execution of the following stage will be triggered even if the task fails.
6. Skip checks.
7. Require approval: means that this task will not be executed until approved by people added in the approvers' list.
   * The task remains blocked until all approvers added in the list approve it.

**Sample output**
