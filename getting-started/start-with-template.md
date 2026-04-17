---
icon: paste
---

# Start with a template

### Overview

Using a template is one of the quickest ways to get started with Brainboard. By providing you with a pre-built architecture that you may modify, templates ensure that you begin with a tried-and-true infrastructure design and save you time during the initial setup.

### Start with Architecture

1. If you already have architectures, click the <mark style="color:$primary;">`Create architecture`</mark> button in the <mark style="color:$primary;">**Recent architectures**</mark> section of the main page.
2. As an alternative, click the <mark style="color:$primary;">`Create architecture`</mark> button in the interface's lower left corner.<br>

<figure><img src="../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

### Select From Template

Once the menu opens, you have three primary paths to start your project:

1. **From scratch**: Start with a blank canvas.
2. **From your infrastructure**: Import existing Terraform files or sync from a cloud provider.
3. **From a template**: Access the catalog of pre-built designs.

Choose <mark style="color:$primary;">**`From a template`**</mark> to gain proceed to the  template catalogue.

<figure><img src="../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

### Choosing a Template

The catalog provides powerful filtering tools to help you find the right architecture. Use the Filters pane on the right side of the screen to narrow your search:

1. <mark style="color:$primary;">**Scope**</mark>: Select the source library for your templates. You can choose :
   1. All Scopes: Displays every template available to you across both public and organizational libraries.
   2. Public: Access a collection of high-quality architecture patterns provided by Brainboard that cover common cloud deployment scenarios.
   3. Organization: Access your company’s internal library of private infrastructure patterns tailored specifically for your team.

{% hint style="info" %}
You can convert any architecture you have designed into a Private Template. This allows you to build a reusable collection of authorized infrastructure patterns, ensuring architectural uniformity and significantly accelerating future deployment cycles.
{% endhint %}

2. <mark style="color:$primary;">**Filter by Provider**</mark>**:** To view templates unique to that environment, choose your desired cloud provider(_<mark style="color:$primary;">AWS, Azure, GCP</mark>_`,` etc.).
3. <mark style="color:$primary;">**Tags**</mark>**:** use the Tags sidebar to filter by specific infrastructure components like `Networking`, `Database`, `Compute`, or `Serverless`, use the `Tags` sidebar.
4. <mark style="color:$primary;">**Search**</mark>**:** To locate particular use cases, such as `landing zone`, `kubernetes`, `security`, utilize the search bar.<br>

<figure><img src="../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

### Sorting your view

You can sort the filtered results by clicking the <mark style="color:$primary;">**`Name`**</mark>**&#x20;dropdown**. Options include sorting by&#x20;

1. Name (ascending/descending)
2. Cloud provider(ascending/descending)
3. date the template was last updated(ascending/descending)

<figure><img src="../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>

### Using a Template

After choosing a template, the visual diagram and associated  `Terraform` code are loaded onto the design canvas where you can:

1. Customize resources by manually renaming parts and changing variables to meet your unique needs.
2. Make use of <mark style="color:$primary;">**Brainy**</mark>: To change the template, use natural language prompts
3. Run Validation: To make sure the template's configuration is accurate inside your particular environment variables, run  `Terraform` Validate.

{% hint style="info" %}
If your team frequently uses the same architecture patterns, storing them as Private Templates guarantees architectural uniformity and significantly speeds up subsequent deployment cycles.
{% endhint %}
