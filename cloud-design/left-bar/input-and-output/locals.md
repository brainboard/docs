# Locals

A **local value** assigns a name to an [expression](https://developer.hashicorp.com/terraform/language/expressions), so you can use the name multiple times within a module instead of repeating the expression.&#x20;

{% hint style="success" %}
<mark style="color:$primary;">**Brainboard**</mark> allows you to define multiple locals.
{% endhint %}

{% hint style="info" %}
When you define locals in **Brainboard**, they are added to the <mark style="color:$primary;">**`locals.tf`**</mark> file and in the same block <mark style="color:$primary;">**`locals`**</mark>&#x20;
{% endhint %}

{% hint style="warning" icon="hand-point-right" %}
_The table of locals is similar to the table of_ [_variables_](variables.md)_. Please refer to it to understand the different components of the user interface._
{% endhint %}

#### Creating a new local

1. Click the <mark style="color:$primary;">**`Locals`**</mark> icon available in the right panel.&#x20;
2. Then, click the <mark style="color:$primary;">**`+`**</mark> icon to add/import variables. It opens the **Create local** modal.
3. Specify the _<mark style="color:$primary;">Name</mark>, <mark style="color:$primary;">Description</mark>_ and _<mark style="color:$primary;">Value</mark>_ of the local.

<figure><img src="../../../.gitbook/assets/creating-locals (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
If you are using a complex expression in the value field, you need to quote it, as you can mix **strings, functions, and variables.**
{% endhint %}
