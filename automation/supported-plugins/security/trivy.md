# Trivy

This plugin allows you to scan the Terraform code with <mark style="color:$primary;">**`trivy`**</mark> and provide output.

{% hint style="info" %}
<mark style="color:$primary;">**`trivy`**</mark> is a static analysis security scanner that can be used for Terraform code.
{% endhint %}

* [Home page](https://trivy.dev/latest/docs/coverage/iac/terraform/)
* [Source code on GitHub](https://github.com/aquasecurity/trivy)

<figure><img src="../../../.gitbook/assets/trivy (1).png" alt=""><figcaption></figcaption></figure>

**Configuration options**

1. **Name:** This is a <mark style="color:$primary;">**Brainboard**</mark> field to describe what this task is about.
2. **Ignore status:** List of vulnerability statuses to ignore:
   1. <mark style="color:$primary;">**`unknown`**</mark>
   2. <mark style="color:$primary;">**`not_affected`**</mark>
   3. <mark style="color:$primary;">**`affected`**</mark>
   4. <mark style="color:$primary;">**`fixed`**</mark>
   5. <mark style="color:$primary;">**`under_investigation`**</mark>
   6. <mark style="color:$primary;">**`will_not_fix`**</mark>
   7. <mark style="color:$primary;">**`fix_deferred`**</mark>
   8. <mark style="color:$primary;">**`end_of_life`**</mark>
3. **Scanners:** List of what security issues to detect:
   1. <mark style="color:$primary;">**`vuln`**</mark>
   2. <mark style="color:$primary;">**`misconfig`**</mark>
   3. <mark style="color:$primary;">**`secret`**</mark>
   4. <mark style="color:$primary;">**`license`**</mark>
4. **Severity:** Severities of security issues to be displayed:
   1. <mark style="color:$primary;">**`UNKNOWN`**</mark>
   2. <mark style="color:$primary;">**`LOW`**</mark>
   3. <mark style="color:$primary;">**`MEDIUM`**</mark>
   4. <mark style="color:$primary;">**`HIGH`**</mark>
   5. <mark style="color:$primary;">**`CRITICAL`**</mark>
5. **Ignore failure:** if enabled, the execution of the following stage will be triggered even if the task fails.
6. **Offline scan:** Do not issue API requests to identify dependencies
7. **Require approval:** It implies that this task will not be executed until approved by people added to the approvers' list.
   * The task remains blocked until all approvers added in the list approve it.
   * When enabled, it allows you to add approvers to the list.
   * The approver has to be a <mark style="color:$primary;">**Brainboard**</mark> user.
8. **Config:** Can be used to pass any valid **Trivy** configuration page (see [documentation](https://trivy.dev/latest/docs/references/configuration/config-file/))
9. **Skip files:** Specify the files or glob patterns to skip.

**Sample output**

The output includes clickable links that open the relevant documentation pages listed in the <mark style="color:$primary;">**'More Information'**</mark> section.

<figure><img src="../../../.gitbook/assets/CleanShot 2025-07-10 at 13.34.35@2x.png" alt=""><figcaption></figcaption></figure>

