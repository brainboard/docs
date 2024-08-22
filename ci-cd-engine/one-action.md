# One action 🏎️

### Description

One action is a way to execute quickly one Terraform action at a time, like terraform plan or apply without triggering the pipeline.

This is useful when you are building the infrastructure to quickly launch a plan or validate to make sure the code is valid and see what changes will be introduced.

![One action](../.gitbook/assets/one-action.png)

### How it works

When you trigger an action in `one-action` tab, Brainboard creates an ephemeral execution environment, execute the action and provides you with the output in real time. You see the timestamp in the bottom on the right in UTC timezone.

This execution will also be logged in the pipeline history, so you can visualize it at any time. You see it as one action pipeline with the action as the name of the task.&#x20;

<figure><img src="../.gitbook/assets/one-action-history.png" alt=""><figcaption></figcaption></figure>

### Actions

Here are the action available in one-action tab:

1. Validate: this will execute `terraform validate` on the generated code and gives you the output.
2. Plan: it will do `terraform plan` on the generated code and gives you the output.
3. Apply: it will do `terraform apply -auto-approve` on the generated code and gives you the output.
4. Destroy: it will do `terraform destroy -auto-approve` on the generated code and gives you the output.

{% hint style="info" %}
Before doing any action, Brainboard does `terraform init -input=false -upgrade=true` to make sure everything is setup correctly before launching the execution of the action.
{% endhint %}

#### Stop the execution

When there is an ongoing execution, you can stop it by clicking on the `Stop` button located in the top-right corner of the output.

![Stop one-action](../.gitbook/assets/stop-one-action.png)

{% hint style="danger" %}
When you stop an ongoing `apply` or `destroy`, Brainboard attempts to gracefully shutdown the execution process, but in some rare cases the Terraform state maybe get corrupted. If you encounter this situation, reach out to our support.
{% endhint %}

### Targeting

Brainboard provides you with the possibility to execute an action on a specific resource. E.g. you want to destroy a specific resource(s) on an already deployed architecture without impacting the whole infrastructure.

To achieve this, type the address of the resource in the menu or select it from the dropdown menu, then click on any action.

{% hint style="info" %}
Refer to [this documentation page](https://developer.hashicorp.com/terraform/cli/commands/plan#resource-targeting) to understand how resource targeting works in Terraform.
{% endhint %}

### Output

Brainboard provides with real-time output of the current execution.

When you first open the one-action tab, Brainboard displays the output of the last execution.

### Best practices

* When you are building a cloud architecture, it's advised to do `plan` frequently to catch errors at early stage and fix them.
* It's advised to have two separate browser windows of Brainboard, one to design and the other one to do plan or trigger pipeline.
