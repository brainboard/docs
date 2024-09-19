---
icon: sliders-up
hidden: true
---

# Account Setup

Here below are setup actions that you need to do for your account to be able to:

* Do pull requests to your repo
* Organize how you work with your team collaboratively
* Do plan, apply and/or destroy

## 0. How data is organized

Before you start, you need to understand how information is organized in Brainboard.

There are 3 levels of information:

![project-env-arch](../.gitbook/assets/project-env-arch.png)

1.  **Projects**: this is the topmost level of the hierarchy and it is equivalent to a folder.

    To better organize your work within Brainboard, you can consider the project as your client or team's folder, so you can rename it in a way that makes sense to you.
2.  **Environments**: inside any given project, you have multiple environments. By default, Brainboard suggests creating 5 environments when you create a project.

    These environments are the stages of production systems, like test, development, QA, staging, production... and they are containers for architectures.
3.  **Architectures**: is the last element in the hierarchy and contains the diagram of your cloud infrastructure with the auto-generated code.

    The architecture is the one that accepts actions like plan, apply and/or destroy, pull requests, versioning...

{% hint style="info" %}
There is always **one Terraform state** per architecture (and one architecture means one Terraform state) to better isolate and secure your infrastructure.
{% endhint %}



Please refer to the right section of every level if you need detailed information.

## 1. Team organization

When you invite your colleagues to build cloud infrastructures within Brainboard, it's better to put them into teams to reflect your internal organization & processes. E.g. DevOps team, Cloud Architect team, Security team, project managers...

Here is the [link](https://app.brainboard.co/settings/teams) to access the team settings.

![team-management](../.gitbook/assets/team-management.png)

## 2. Add cloud credentials

Add your preferred cloud provider credentials to be able to do plan, apply or destroy and also to trigger the CI/CD pipelines.

Here is the [link](https://app.brainboard.co/settings/cloud-providers) to access the cloud credentials page.

![AWS creds](../.gitbook/assets/aws-creds.png) ![Azure creds](../.gitbook/assets/azure-creds.png)

## 3. Git configuration

[Brainboard supports 2 types of Git connections:](#user-content-fn-1)[^1]

### Git apps

This type of connection is done through the app registration, and the user management is done at your provider level and not in Brainboard

Only GitHub is a Git app in Brainboard.

Here is the [link](https://app.brainboard.co/settings/git-apps) to access the Git apps settings page.

![Git apps](../.gitbook/assets/git-apps.png)

### 3.2. Add personal git tokens

The git personal tokens page allows you to store the tokens that you generate from your Git provider and set their scope (in which projects they will be used).

The Git providers supported are:

* Azure DevOps
* GitHub
* Gitlab
* Bitbucket

Here is the [link](https://app.brainboard.co/settings/personal-git-tokens) to access the Git personal settings page.

![Gitlab personal tokens](../.gitbook/assets/gitlab-personal-tokens.png)

## 4. Set remote backend

It's a best practice to store the Terraform state generated after you provision your cloud infrastructure into a remote backend.

Brainboard allows you to set and use your own remote backend.

Here is the [link](https://app.brainboard.co/settings/data) to configure it.

![Terraform remote backend](<../.gitbook/assets/remote-backend (1).png>)

[^1]: GitHub is a Git app.
