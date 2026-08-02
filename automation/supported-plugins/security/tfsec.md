# Tfsec

This plugin allows you to scan the **Terraform** code with <mark style="color:$primary;">**`tfsec`**</mark> and provide output.

{% hint style="info" %}
<mark style="color:$primary;">**`tfsec`**</mark> is a static analysis security scanner for your **Terraform** code.
{% endhint %}

* [Home page](https://aquasecurity.github.io/tfsec)
* [Source code on GitHub](https://github.com/aquasecurity/tfsec)

**Configuration options**

1. **Name:** This is a <mark style="color:$primary;">**Brainboard**</mark> field to describe what this task is about.
2. **Disable grouping:** Disable grouping of similar results.
3. **Ignore failure**: This will put the task in a non-blocking failure, which means the execution of the following stage will be triggered even if the task fails.
4. **Include ignored:** Include ignored checks in the result output.
5. **Include passed:** Include passed checks in the result output.
6. **Require approval:** It implies that this task will not be executed until approved by people added in the approvers' list.
   * The task remains blocked until all approvers added in the list approve it.
   * When enabled, it allows you to add approvers to the list
   * The approver has to be a <mark style="color:$primary;">**Brainboard**</mark> user.<br>
7. **Minimum severity:** You can specify the minimum severity of result that should be reported. By default, every severity is reported. You must use one of <mark style="color:$primary;">**`CRITICAL`**</mark><mark style="color:$primary;">**,**</mark><mark style="color:$primary;">**&#x20;**</mark><mark style="color:$primary;">**`HIGH`**</mark><mark style="color:$primary;">**,**</mark><mark style="color:$primary;">**&#x20;**</mark><mark style="color:$primary;">**`MEDIUM`**</mark><mark style="color:$primary;">**,**</mark><mark style="color:$primary;">**&#x20;**</mark><mark style="color:$primary;">**`LOW`**</mark>.
8. **Disabled checks:** comma-separated list of checks to exclude during the execution.
   1. This list has to be in this format: <mark style="color:$primary;">**`rule1,rule2,rule3...`**</mark>
   2. No space should be added after the comma in the list.

<figure><img src="/broken/files/fo22n4q0FdL5qup7PxNG" alt=""><figcaption></figcaption></figure>

**Sample output**

The output includes clickable links that open the relevant documentation pages listed in the <mark style="color:$primary;">**'More Information'**</mark> section.

<figure><img src="../../../.gitbook/assets/CleanShot 2025-07-10 at 13.24.02@2x.png" alt=""><figcaption></figcaption></figure>

