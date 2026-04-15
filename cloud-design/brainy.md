---
description: >-
  Design, modify, troubleshoot and validate your cloud architecture using
  natural language.
icon: brain-circuit
---

# Brainy

{% hint style="info" %}
This feature is in an **alpha stage** and open only to select users and customers through a waiting list.
{% endhint %}

## Overview

<mark style="color:$primary;">**Brainy**</mark> is an AI-powered assistant built directly into your Brainboard architecture workspace. It allows you to design, modify, troubleshoot, and validate cloud infrastructure using natural language.

Instead of manually configuring resources, you can simply describe what you want, and <mark style="color:$primary;">**Brainy**</mark> will update your architecture diagram and generate the corresponding Terraform configuration in real time.

Powered by advanced AI models (Anthropic Claude Sonnet 4.6 and Opus 4.6), <mark style="color:$primary;">**Brainy**</mark> acts as an intelligent co-pilot for infrastructure design, helping you move faster while maintaining full control and visibility.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
It can take a while for <mark style="color:$primary;">**Brainy**</mark> to analyze the existing architecture, think, and generate results for the requested design configuration. However, you can view continuous progress in both the chat area and the design canvas.&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

***

## Key Capabilities

### 1. Real-Time Architecture Editing

<mark style="color:$primary;">**Brainy**</mark> can directly modify your diagram based on your instructions:

* Add new resources (AWS, Azure, GCP, etc.).
* Update existing components.
* Remove unnecessary resources.
* Create and manage supporting files (e.g., scripts, IAM policies).

### 2. Terraform Configuration Management

<mark style="color:$primary;">**Brainy**</mark> automatically handles Terraform configurations, including:

* Resource attributes and blocks.
* Variables, locals, and outputs.
* Structured and clean Terraform code generation.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### 3. Module Integration

You can use modules directly from your organization’s module catalog.

* Reuse predefined infrastructure components.
* Maintain consistency across projects.
* Speed up complex deployments.

{% hint style="warning" %}
Currently, <mark style="color:$primary;">**Brainy**</mark> can access only the modules that are already imported into Brainboard.
{% endhint %}

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

#### 4. Built-in validation

<mark style="color:$primary;">**Brainy**</mark> helps ensure your infrastructure is correct and deployable:

* Run `terraform plan`
* Run `terraform validate`
* Detect issues and fix them, for example:
  * Circular dependencies
  * Resources misconfiguration
  * Hierarchy problems

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

### 5. Pipeline Visibility

<mark style="color:$primary;">**Brainy**</mark> allows you to:

* View pipeline execution history.
* Access job logs.
* Understand what changes are being proposed.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### 6. Documentation Generation

When requested, <mark style="color:$primary;">**Brainy**</mark> can:

* Generate architecture README files.
* Update documentation as your system evolves.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### 7. Context Reference using <mark style="color:$primary;">@</mark>&#x20;

In your prompt/command, you can mention a specific node or a resource that's used in your architecture design by using the <mark style="color:$primary;">**@**</mark> sign, and you will be presented with the list of the currently opened architecture resources/nodes. Once you start typing the resource/node name, the list will be filtered accordingly for you to choose your desired node.&#x20;

<figure><img src="../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
The node names will appear in the list as the original resource names, and not at the node title.&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

***

#### 8. Insights into Brainy's processing

By expanding the **Thought** option, you can also view <mark style="color:$primary;">**Brainy's**</mark> process or logic, based on which it gave you the results or responded to you.&#x20;

<figure><img src="../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

#### 9. Exporting Chat as a Markdown file

You can export the transcript of your chat with <mark style="color:$primary;">**Brainy**</mark> as a markdown (MD) file. To do so, simply click on the **vertical ellipsis** (the three dots) in the top right corner of the chat, and select the **`Export transcript`** option from the dropdown menu.&#x20;

<figure><img src="../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>



***

#### 10. Redo/Undo changes

Whenever you make changes to your architecture design using <mark style="color:$primary;">**Brainy**</mark>, a clickable **Undo** option becomes available just below the last <mark style="color:$primary;">**Brainy's**</mark> message from Brainy confirming the change. Clicking on it will revert all the changes that were made up to that point in your current session of chat.&#x20;

{% hint style="info" %}
* <mark style="color:$primary;">**Brainy**</mark> holds the history of changes that were made within the last 24 hours.&#x20;
* Any changes made before the last 24 hours are discarded, except the last 10 changes that are older than 24 hours. In short, only the last 10 changes older than 24 hours are reversible.&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

You can also redo/undo changes using a prompt in the chat. However, the 24-hour rule for undo remains the same.&#x20;

<figure><img src="../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

***

## Accessing Chat History

To access the <mark style="color:$primary;">**Brainy**</mark> chat history for any architecture design, simply launch the Brainy chat window, and there you will see the list of past chat sessions. You can also view the time it was created. For example, 30 minutes ago, 10 days ago, etc.&#x20;

Click on any session that you want to view or continue with.&#x20;

<figure><img src="../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

## Limitations

To ensure safety and control, <mark style="color:$primary;">**Brainy**</mark> has the following limitations:

* It cannot run `terraform apply` or `destroy.`
* It cannot access the internet.
* It cannot modify `providers.tf` (system-managed).
* It is limited to one architecture per conversation.
* It has no access to Terraform state files.
* It does not support user/org/permission management.
* It is focused only on cloud/infrastructure topics.
* It does not have a BYOK / self-hosted option yet (Brainboard team is collecting feedback).
* It supports only image files as attachments. Exported chat transcripts (md files), and PDF files are not supported as uploads/attachments as of now.&#x20;

***

## Data & Privacy

<mark style="color:$primary;">**Brainy**</mark> is built with privacy and security in mind.

#### What is Shared with the AI

* Architecture content (resources, TF configs, variables, outputs).
* Conversation messages.
* Architecture metadata (name, description, provider versions).

#### What is NOT Shared

* Terraform state files.
* Credentials or secrets.
* Other architectures.
* Personal data.

#### Zero Data Retention (ZDR)

<mark style="color:$primary;">**Brainy**</mark> uses [Anthropic’s Zero Data Retention](https://platform.claude.com/docs/en/build-with-claude/api-and-data-retention) policy:

* No data is stored.
* No data is used for training.

***

## Alpha Access

<mark style="color:$primary;">**Brainy**</mark> is currently available in **alpha,** and the steps for alpha access are:&#x20;

1. Join the waiting list.
2. The feature is enabled via a flag.
3. Receive documentation and walkthrough.
4. Provide feedback to maintain access.

{% hint style="warning" %}
Access is revoked if there is no usage for two weeks or no feedback is provided after follow-up.
{% endhint %}

{% hint style="info" %}
The feature is free during the alpha preview.
{% endhint %}

***

## Reporting Issues

When reporting an issue or providing feedback, it is recommended to copy the <mark style="color:$primary;">**conversation ID**</mark> of the chat you used to test <mark style="color:$primary;">**Brainy**</mark>.&#x20;

To copy the conversation ID, click on the **vertical ellipsis** (the three dots) in the top right corner of the chat, and select the **`Copy conversation ID`** option from the dropdown menu.&#x20;

<figure><img src="../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

***

## Frequently Asked Questions

1. **Is&#x20;**<mark style="color:$primary;">**Brainy**</mark>**&#x20;free?**\
   <mark style="color:green;">**Yes**</mark>, during the alpha phase.
2. **Can it deploy infrastructure?**\
   <mark style="color:$danger;">**No**</mark>. It only supports <mark style="color:$primary;">**`plan`**</mark> and <mark style="color:$primary;">**`validate`**</mark>**.**
3. **Does it access the internet?**\
   No, but it has built-in knowledge of public modules.
4. **Can it make mistakes?**\
   Yes. You can:
   1. Ask it to fix issues.
   2. Revert using conversation checkpoints.
5. **Which cloud providers are supported?**\
   All providers supported by Brainboard (AWS, Azure, GCP, etc.)
