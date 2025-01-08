# OPA

This plugin allows you to check your Terraform code against security policies that you define.

`OPA` is a policy-based control for cloud native environments.

* [Home page](https://www.openpolicyagent.org/).
* [Source code on Github](https://github.com/open-policy-agent/opa).

![OPA plugin](../../../.gitbook/assets/opa-plugin.png)

### **Configuration options**

1. Policy: the content of `rego` file that contains your policy.
2. Version: always points to the latest version.
3. Decision.
4. Ignore failure: if enabled, the execution of the following stage will be triggered even if the task fails.
5. Require approval: means that this task will not be executed until approved by people added in the approvers' list.
   * The task remains blocked until all approvers added in the list approve it.

### **Sample output**



### Examples

#### Naming convention

<pre class="language-rego"><code class="lang-rego">package brainboard

deny contains msg if {
    r := input.resource_changes[_]
    r.type == "azurerm_storage_account"
    not startswith(r.change.after.name, "bb")
    
    msg := sprintf("%v must start with bb", [r.address])
}


deny contains msg if {
<strong>    r := input.resource_changes[_]
</strong>    r.type == "azurerm_resource_group"
    not startswith(r.change.after.name, "bb-")
    
    msg := sprintf("%v must start with bb-", [r.address])
}

</code></pre>

Decision: `brainboard/deny`

#### Mandatory tags

```rego
package brainboard

required_tags := ["Environment", "Owner"]

deny contains msg if {
	r := input.resource_changes[_]
	missing_tags := {tag | tag := required_tags[_]; not r.change.after.tags[tag]}

	msg = sprintf("Resource is missing required tags: %v (%v)", [r.address, missing_tags[_]])
}
```

Decision: `brainboard/deny`

#### Unrestricted ingress for AWS Security Group

```rego
package brainboard 

deny contains msg if {
  r := input.resource_changes[_]
  r.change.after.ingress[_].cidr_blocks[_] == "0.0.0.0/0"
  msg := sprintf("%v has 0.0.0.0/0 as allowed ingress", [r.address])
}
```

Decision: `brainboard/deny`

