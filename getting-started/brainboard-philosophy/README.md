---
icon: sparkles
---

# Brainboard philosophy

{% hint style="info" %}
Brainboard has been built by engineers for engineers, and we started it as we were scratching our own itches.
{% endhint %}

### Background story

What was eye-opening to us at the beginning was to realize that most engineers go through the exact same steps to create a cloud infrastructure:

1. They start with a high-level design (HLD) on a whiteboard, paper, or even in the head of the engineer.&#x20;

‼️ Even if you are building the infrastructure without a design, you have it in your mind. For example: This database will be in this security group, connected to this application, with this data flow, behind this load balancer, etc.&#x20;

⚠️ If the team doesn't have a design, no one can review the architecture, and this usually leads to communication barriers.

2. When the design is done, they will translate it into code. Whether the code is written by the same team or a different one doesn't make any difference; the workflow stays the same.
3. This Terraform code will first be checked if it's valid (terraform plan or validate), then scanned for security, policies, naming conventions, costs, etc.&#x20;

{% hint style="info" %}
This is what is called [shift left](../../help-and-faq/glossary.md#shift-left) in the industry, where the feedback loop has to be short. You detect errors as early as possible, fix them and iterate until you are ready to deploy. Actually, not yet, as most of the time, you need to change the design a bit to make it match the Terraform implementation.
{% endhint %}

2. Once the design and code are validated, the deployment process starts either automatically or manually, with or without approval.\
   \
   ⇒ If it's automatic, it will be done through the CI/CD.
3. Then, come all the heavy things like managing secrets, collaboration with different people in the same team, cross teams, deploying multiple environments and the most painful of all is the drift.

‼️ It needs discipline to respect the process for every single change you have to do, and since it relies on humans, some of them just fall into the old habit, going straight to the console of the cloud provider and changing things manually.

💡At this point, let's assume that all the steps are aligned, and you provision the infrastructure successfully, then every change you want to introduce has to go through the same steps again and again. It's not a negative statement, by the way, it's just how the process should work.



<figure><img src="../../.gitbook/assets/ChatGPT Image May 11, 2026, 06_49_19 PM.png" alt=""><figcaption></figcaption></figure>

### What did the engineers want?

We, as engineers, wanted this to change! We wanted it so badly that we said to ourselves, let's write a wish list: what we want in an ideal world? We started writing down:

* First, we wanted to rely on automation and didn't want to repeat ourselves, in a way that when we design, the code is automatically generated. Let's focus on Terraform, it's the most used one. OK!
* But we wanted to still have control over the code and be able to do what we are used to doing in Terraform: variables, outputs, loops, data blocks, modules, etc, and be able to manage multiple environments easily. No more manual tasks, please.
* And wanted to have the shortest feedback loop possible, so why not an embedded CI/CD with all the tools we use: tfsec, checkov, terrascan, OPA, infracost.
  * Oh, security should be a native part. No more running after engineers to comply and rely on discipline.
* We also wanted to push the boundaries, because it's not about the tool itself but the workflow, and wondered why not having a reference architecture catalogue available to anyone within the team, and we finally stopped reinventing the wheel. Sounds amazing, right?
* Finally, we dreamed about making it enterprise-ready with RBACs, private runners, live collaboration, SSO, private registries, and the list didn't stop.&#x20;

<figure><img src="../../.gitbook/assets/ChatGPT Image May 11, 2026, 06_51_30 PM.png" alt=""><figcaption></figcaption></figure>

> _**Fast-forward, a few years later,****&#x20;**<mark style="color:$primary;">**Brainboard**</mark>**&#x20;****becomes the one platform of choice for end-to-end cloud infrastructure management that offers exactly the wish list we dreamed about.**_
>
> _**Delivered and supported by the most talented engineers in the cloud, IaC and software engineering.**_

