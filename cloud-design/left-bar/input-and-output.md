# Input & output

### Overview

When you design your cloud infrastructures in Brainboard, the <mark style="color:$primary;">Terraform</mark> code is auto-generated for you based on the configuration of the resources.&#x20;

{% hint style="info" %}
Brainboard allows you to use **variables, locals** and **output** exactly as you would do it in Terraform.
{% endhint %}

{% hint style="success" %}
You can implement your naming conventions, set specific values for the configuration based on some criteria and define what information you want to display once the infrastructure is deployed.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (17).png" alt="" width="434"><figcaption></figcaption></figure>

***

### Variables

In Terraform, a variable is a way to store and reuse values throughout your Terraform code, and it is defined using the `variable` block.

When you click on the  `Variable` button available in the left panel, it opens the **Variables** window.

{% hint style="info" %}
Brainboard follows Terraform best practices, so by default, when you create a new architecture, Brainboard automatically adds a variable called `tags` which is added in the generated Terraform code of every resource that supports tagging.
{% endhint %}

#### Action items on the Variables window

Shared below is the screenshot of the Variables window, numbered with action items/features available on this screen, followed by their brief description.&#x20;

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="57">#</th><th width="138">Feature</th><th width="563.6666259765625">Purpose / Description</th></tr></thead><tbody><tr><td><sub>1</sub></td><td><sub><strong>Add Variable</strong></sub></td><td><sub>To create a new variable. <em>(Explained in detail below).</em></sub></td></tr><tr><td><sub>2</sub></td><td><sub><strong>Search bar</strong></sub></td><td><sub>To search for a specific variable on the Variables window. Keyword search is supported.</sub></td></tr><tr><td><sub>3</sub></td><td><sub><strong>Switch view</strong></sub></td><td><p></p><p><sub>Using these buttons, you can switch between a detailed and a compact view of the variables list.</sub> </p></td></tr><tr><td><sub>4</sub></td><td><sub><strong>Sorting variables list</strong></sub></td><td><sub>You can sort the list of variables according to ascending or descending order of their names, as well as in ascending/descending order of the date when they were last updated.</sub> </td></tr><tr><td><sub>5</sub></td><td><sub><strong>Scope view</strong></sub></td><td><sub>The scope selector allows you to view variables that are defined in every scope or display all variables of all scopes.</sub></td></tr><tr><td><sub>6</sub></td><td><sub><strong>Variable list</strong></sub></td><td> <sub>By default, the variables list is displayed in the"detailed view", which shows more information about variables than just names.</sub></td></tr></tbody></table>

#### Creating a new variable

To create a new variable, click on the  `Add Variable` button on the **Variables** window, and a form will appear on the right side of the screen _(explained below the screenshot)._&#x20;

<figure><img src="../../.gitbook/assets/image (30).png" alt="" width="375"><figcaption></figcaption></figure>



On the _"create new variable"_ form, you can specify the following information:

1. **Name of the variable:** This is the name that you'll use to reference the variable when you use it.&#x20;

{% hint style="info" %}
It follows the naming conventions of Terraform, for example, it doesn't support spaces, or starting with a number.

**Best practice:** use clear and explicit names and separate words with underscore `_`.
{% endhint %}

2. **Scope:** You can set the level where you want this variable to be available.

<figure><img src="../../.gitbook/assets/image (32).png" alt="" width="156"><figcaption></figcaption></figure>

{% hint style="info" %}
The four levels of scopes are listed in the order of "least shared or restrictive to more shared / available/"
{% endhint %}

{% hint style="info" %}
There is an override mechanism if the same variable is defined in multiple scopes.&#x20;
{% endhint %}

<table><thead><tr><th width="175.66668701171875">Scope</th><th width="270.6666259765625">Explana</th><th>No</th></tr></thead><tbody><tr><td><sub><strong>Architecture</strong></sub></td><td><sub>Variables that are defined with this scope are only available within this architecture only.</sub></td><td><sub>If the same variable is defined in another level as well, the default or values defined at the architecture level overrides any other level.</sub> </td></tr><tr><td><sub><strong>Environment</strong></sub></td><td><sub>Variables defined at the environment level are available to all architectures within the same environment.</sub></td><td><sub>Variables defined in this level override those defined at project and organization level.</sub> </td></tr><tr><td><sub><strong>Project</strong></sub></td><td><sub>Variables defined at the project level are available to all environments and architectures within the same project.</sub></td><td><sub>Variables defined in this level override those defined at the organization level.</sub> </td></tr><tr><td><sub><strong>Organization</strong></sub></td><td><sub>Variables defined at the organization level are available to all architectures, environments and project within the organization.</sub></td><td></td></tr></tbody></table>

3. **Description:** It should concisely explain the purpose of the variable and what kind of value is expected. This description string might be included in documentation about the module, and so it should be written from the perspective of the user of the module rather than its maintainer.
4. **Variable type:** This allows you to restrict the type of value that will be accepted.&#x20;

{% hint style="info" %}
If no type constraint is set then a value of any type is accepted.
{% endhint %}

While type constraints are optional, we recommend specifying them; they can serve as helpful reminders for users of the module, and they allow **Terraform** to return a helpful error message if the wrong type is used.

{% hint style="success" %}
The supported type keywords are: `any` `bool` `list` `map` `number` `object` `set` `string` `tuple`
{% endhint %}

<figure><img src="../../.gitbook/assets/image (33).png" alt="" width="375"><figcaption></figcaption></figure>

5. **Default value:** If present, the variable is considered to be _<mark style="color:$primary;">optional</mark>_ and the default value will be used if no value is set.
6. **Value:** The value that will be used during **Terraform** execution and if defined, it overrides the default value.
   1. This value will be put in the file `terraform.tfvars` .
   2. If you convert the architecture into a template or clone the architecture, this value will be removed.
7. **Sensitive:** Setting this flag prevents **Terraform** from showing its value in the `plan` or `apply` output and Brainboard will store the variable in a separate vault.

{% hint style="warning" %}
Even if the variable is flagged sensitive, its value will still be stored in clear text in the Terraform state.
{% endhint %}

8. **Validation:** You can specify custom validation rules for the variable.

{% hint style="info" %}
For every variable defined, Brainboard creates a variable block in the file `variables.tf.`
{% endhint %}

{% hint style="info" %}
Refer to the RBAC (Role Based Access Control) documentation page to understand how you can manage permissions to restrict/allow members and teams to add, update or delete variables.
{% endhint %}

***

### Locals

A **local value** assigns a name to an [expression](https://developer.hashicorp.com/terraform/language/expressions), so you can use the name multiple times within a module instead of repeating the expression.&#x20;

Brainboard allows you to define multiple locals.

{% hint style="success" %}
When you define locals in Brainboard, they are added to the `locals.tf` file and in the same block `locals`&#x20;
{% endhint %}

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

_The table of locals is similar to the one of variables detailed above. Please refer to it to understand the different components of the user interface._

#### Creating a new local

Click on the  `Add local` button to open the modal that allows you to specify the _<mark style="color:$primary;">Name</mark>, <mark style="color:$primary;">Description</mark>_ and _<mark style="color:$primary;">Value</mark>_ of the local.

<figure><img src="../../.gitbook/assets/image (27).png" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="info" %}
If you are using a complex expression in the value field, you need to quote it as you can mix strings, functions, variables....
{% endhint %}

***

### Outputs

**Output values** make information about your cloud infrastructure available on the **command line** and will be displayed in the output of execution.

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

_The table of output is similar to the one of variables detailed above. Please refer to it to understand the different components of the user interface._

#### Creating an output

Click on the `Add output` button to open the modal that allows you to specify the _<mark style="color:$primary;">Name</mark>, <mark style="color:$primary;">Description</mark>_ and _<mark style="color:$primary;">Value</mark>_ of the output.

<figure><img src="../../.gitbook/assets/image (29).png" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="success" %}
For every output defined, Brainboard creates an output block in the file `outputs.tf`.
{% endhint %}
