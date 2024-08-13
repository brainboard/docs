# Frequently Asked Questions 👋

### Do I need to be Terraform expert to use Brainboard?

No. You don't need to be a Terraform or IaC expert to use Brainboard. But minimum knowledge of Terraform is required to fully take advantage of Brainboard.

In fact, Brainboard simplifies the complexity of Terraform and helps you configure cloud resources with a configuration menu. It will then write clean Terraform code for you, according to best practices.

🎒 We also help the community by providing free Terraform trainings, that you can find in our [Youtube channel](https://www.youtube.com/channel/UCB0DLhFEgta83U62mQzxGPg).

### What is the difference between Brainboard and vanilla Terraform?

Terraform is a powerful IaC tool that deploys the code you write.

Brainboard, on the other hand, is an end-to-end cloud management solution built on top of Terraform with a visual architecture designer, where the Terraform code is automatically generated. It also has a secure CI/CD engine, native Git integrations and more features to help you standardize and centralize your cloud.

### Which git providers does Brainboard support?

The following git providers are supported:

* Github
* GitLab
* Azure DevOps
* BitBucket

:::note Request your git provider If your git repository is not listed here, you can request it in our [public roadmap](https://roadmap.brainboard.co). :::

### How does Brainboard integrate with my current workflows?

In brainboard, you are able to include all your current workflows:

* Manage all your Terraform States.
* Setup the Git integration in Brainboard to be able to do pull requests and import existing code.
* Create replicable templates for you and your team to use.
* Import your Terraform modules from a registry, locally or git.

### Can I migrate my existing infrastructure into Brainboard?

You have the possibility to import your existing infrastructure and auto-generate the diagram.

We support importing any file that contains a valid Terraform code.

There are 2 ways to do it:

1. Provide the URL of the Git repo (Github, Gitlab, Bitbucket...)
2. Upload one or multiple files

### Is there a hosted version of Brainboard?

Yes, we provide a self-hosted version based on eligibility criteria.

If you are interested in the hosted version [Contact us](https://www.brainboard.co/resources/contact-sales).

### What are the supported cloud providers?

The following providers are supported:

* Azure
* AWS
* OCI
* GCP
* Scaleway.

You can request (or vote for) your cloud provider to be added it in our [public roadmap](https://roadmap.brainboard.co/boards/feature-requests).

### How often you update cloud providers?

The update process is automatic.

As soon as a new version is released, we automatically trigger the update process that will do extensive tests.

Tests usually take up to 48h to complete, and if they are successful we release the new version automatically.

### Can I deploy my architecture with Brainboard?

Brainboard has an innovative CI/CD engine dedicated for the infrastructure, where you can execute all Terraform actions (Terraform plan, Terraform apply, Terraform destroy) within a secure sandbox and get the output in real time or build your deployment workflow and trigger it.

### How can I collaborate with my colleagues?

There are 2 aspects in terms of collaboration:

1. Build: Brainboard supports real time editing of the same architecture by multiple users. All you need to do is to invite your colleagues and give them the right access.
2. Deploy: when you build your CI/CD pipeline within Brainboard, you have the possibility to request approvals from any team/person, which allows you to orchestrate the execution by involving all stakeholders.

### How does Brainboard integrate tools like Infracost, Checkov, Tfsec, ServiceNow, etc…?

Brainboard allows you to build your pipelines with its innovative and powerful CI/CD engine, where you can just pick the tools you are used to use and configure them easily.

Brainboard maintains these tools for you, so you don't worry about upgrading them automatically or troubleshooting when things go wrong.

Refer to the [supported plugins](https://gitlab.com/brainboard/brainboard/-/blob/main/ci-cd-engine/supported-plugins/README.md) page for more details.

### Can I create templates for my cloud infrastructures?

Brainboard allows you to create a template from any architecture you have. By doing so, you build your internal catalog of templates that any one within your organization can use off the shelf without reinventing the wheel.

### Is Brainboard free?

Yes, there is a free version of Brainboard.

When you sign up, you have 21 days free trial that gives you access to all feature of Brainboard, after that, if you don't upgrade you'll be automatically put in the free tier.

### How do I generate the Terraform code for my cloud architecture?

The Terraform code is automatically generated for you cloud architecture as you design.

### Is SSO supported?

Yes, in the enterprise version. We support both SAML and OAUTH.

### How can I request a demo for Brainboard?

Reach out to one of our sales team at `sales@brainboard.co`.
