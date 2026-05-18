---
icon: paste
---

# Start with a template

### Overview

Using a template is one of the quickest ways to get started with Brainboard. By providing you with pre-built architecture templates, we ensure that you begin with a tried-and-true infrastructure design and save your time during the initial setup. You can always edit these templates as you need.&#x20;

### **Starting with a template**

Here are the steps you can follow to begin with templates:&#x20;

1. Once you are logged into your Brainboard account, navigate to the home page by clicking <mark style="color:$primary;">Home</mark> in the left menu.&#x20;
2. Then, click <mark style="color:$primary;">`Create architecture`</mark> button in the <mark style="color:$primary;">**Recent architectures**</mark> section. As an alternative, you can click the <mark style="color:$primary;">`Create architecture`</mark> button available at the bottom of the left menu.&#x20;

{% hint style="info" %}
As an alternative to the first two steps mentioned above, you can simply click on the <mark style="color:$primary;">**`Templates`**</mark> option in the left menu to begin with templates.&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>



Once the menu opens, you have the following three primary paths to start your project.&#x20;

* **From scratch**: Start with a blank canvas.
* **From your infrastructure**: Import existing Terraform files or sync from a cloud provider.
* **From a template**: Access the catalogue of pre-built designs.

3. Choose <mark style="color:$primary;">**`From a template`**</mark> to gain access to the template catalogue.

<figure><img src="../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>



4. Next, to use the desired template, select it on the <mark style="color:$primary;">**Start from a template**</mark> screen by simply clicking on it.&#x20;
5. Once you have selected your desired template, click the <mark style="color:$primary;">**`Use template`**</mark> option on the next screen. Here, you will be prompted with the <mark style="color:$primary;">**Create architecture from template**</mark> popup modal to confirm the template details.&#x20;
   1. On top of this pop-up modal, you can view the total number of resources that are used in the selected template.&#x20;
   2. **Project:** You can select the project to associate the new architecture design with.&#x20;
   3. **Environment:** You can select the desired environment here. For example, **Development, UAT**, etc.&#x20;
   4. **Architecture name:** Edit the name of the new architecture as you need.&#x20;
   5. **Architecture description:** Provide any additional details of the architecture design.&#x20;

Once you have finalised the new architecture details, you can click the <mark style="color:$primary;">**`Create architecture`**</mark> button given at the bottom right corner of the modal.&#x20;



<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

You will be navigated to the Brainboard canvas, where you can review your design and make further changes.&#x20;

***

### Using a Template

After choosing a template, the visual diagram and associated  `Terraform` code is loaded onto the design canvas, where you can:

1. Customize resources by manually renaming parts and changing variables to meet your unique needs.
2. Make use of <mark style="color:$primary;">**Brainy**</mark>: To change the template, use natural language prompts
3. Run Validation: To make sure the template's configuration is accurate inside your particular environment variables, run  `Terraform` Validate.

{% hint style="info" %}
If your team frequently uses the same architecture patterns, storing them as **Private Templates** guarantees architectural uniformity and significantly speeds up subsequent deployment cycles.
{% endhint %}

***

Shared below is additional information to help you sort the template that best fits your needs.&#x20;

### Filtering Templates

The templates catalogue screen provides powerful filtering tools to help you find the right architecture.&#x20;

<mark style="color:$primary;">**Filters:**</mark> If you click on this option, the <mark style="color:$primary;">**Filters**</mark> pane will be expanded on the right side of the screen. where you can filter designs by:&#x20;

* **Scope**
* **Terraform Providers**
* **Tags**

{% hint style="success" %}
<mark style="color:$primary;">**Scope**</mark>: Select the source library for your templates. You can choose :

1. **All Scopes:** Displays every template available to you across both public and organizational libraries.
2. **Public:** Access a collection of high-quality architecture patterns provided by Brainboard that cover common cloud deployment scenarios.
3. **Organization:** Access your company’s internal library of private infrastructure patterns tailored specifically for your team.
{% endhint %}

{% hint style="success" %}
<mark style="color:$primary;">**Terraform Providers**</mark>**:** To view templates unique to that environment, choose your desired cloud provider(_<mark style="color:$primary;">AWS, Azure, GCP</mark>_`,` etc.).
{% endhint %}

{% hint style="success" %}
<mark style="color:$primary;">**Tags**</mark>**:** Using tags, you can filter the specific infrastructure components like `Networking`, `Database`, `Compute`, or`Serverless`, etc.&#x20;
{% endhint %}

{% hint style="info" %}
You can convert any architecture you have designed into a Private Template. This allows you to build a reusable collection of authorized infrastructure patterns, ensuring architectural uniformity and significantly accelerating future deployment cycles.
{% endhint %}



<mark style="color:$primary;">**Search bar**</mark>**:** To locate particular use cases, such as `landing zone`, `kubernetes`, `security`, you can utilize the search bar.<br>

<figure><img src="../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>



5. To make your view more user-friendly when selecting the desired filter, you can sort the filtered results by clicking the <mark style="color:$primary;">**`Name`**</mark>**&#x20;dropdown**. Options include sorting by&#x20;

* Name (ascending/descending)
* Cloud provider(ascending/descending)
* date the template was last updated(ascending/descending)

<figure><img src="../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>
