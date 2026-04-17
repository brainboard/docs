---
icon: paste
---

# Start with a template

### Overview

Using a template is one of the quickest ways to get started with Brainboard. By providing you with a pre-built architecture that you may modify, templates ensure that you begin with a tried-and-true infrastructure design and save you time during the initial setup.

### Start with Architecture

1. Click on the <mark style="color:$primary;">`New architecture`</mark> button in the top left part.
2. As an alternative, you can click the <mark style="color:$primary;">`Create architecture`</mark> button located in the "Recent architectures" section of the main page of your company.



<figure><img src="../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

### Select From Template

* A number of options for starting your project will be shown to you. To access the global template collection, select <mark style="color:$primary;">`From a template`</mark><mark style="color:$primary;">.</mark>

<figure><img src="../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

### Choosing a Template

It will open the template catalog where you can search for your use case,&#x20;

1. <mark style="color:$primary;">**Search**</mark>**:** To locate particular use cases, such as `landing zone`, `kubernetes`, `security`, utilize the search bar.
2. <mark style="color:$primary;">**Filter by Provider**</mark>**:** To view templates unique to that environment, choose your favorite cloud provider(_<mark style="color:$primary;">AWS, Azure, GCP</mark>_`,` etc.).
3. <mark style="color:$primary;">**Tags**</mark>**:** To filter by infrastructure components like `Networking`, `Database`, `Compute`, or `Serverless`, use the `Tags` sidebar.\
   <br>

<figure><img src="../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

### Template Types

{% hint style="info" %}
There are 2 types of templates: **public** and **private.**\
You can convert any architecture created into a template. Which allows you to build your internal library of templates.
{% endhint %}

Brain board manages two distinct libraries

1. **Public Templates:** Patterns covering common cloud deployments that are accessible to all Brainboard users.
2. **Private Templates:** The internal library of your company. Your team can construct a reusable collection of authorized infrastructure patterns by turning any architecture you have designed into a template.

<figure><img src="../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>

### Using a Template

After choosing a template, the visual diagram and associated  `Terraform` code are loaded onto the design canvas.

1. Customize resources by manually renaming parts and changing variables to meet your unique needs.
2. Make use of <mark style="color:$primary;">**Brainy**</mark>: To change the template, use natural language prompts
3. Run Validation: To make sure the template's configuration is accurate inside your particular environment variables, run  `Terraform` Validate.

{% hint style="info" %}
If your team frequently uses the same architecture patterns, storing them as Private Templates guarantees architectural uniformity and significantly speeds up subsequent deployment cycles.
{% endhint %}
