# Projects 🗂️

### Definition

A project is a container of environments and architectures on which teams have specific permissions.

Think of a project as the upper level folder.

{% hint style="info" %}
&#x20;By default, members don't have direct permissions on projects
{% endhint %}

### Create a new project

To create a new project:

* Go to the [projects setting page](https://app.brainboard.co/settings/projects).
*   Click on the `Create project` button

    ![Create a project](../.gitbook/assets/create-new-project.png)
* You will then go through a project creation wizard.
  * In the first step of the wizard you will setup the name, description and environments of the new project. Brainboard creates 5 environments by default: Production, Staging, Development, Test and QA, but you can add any custom environment as well. The project name and at least one environment are required.
  * In the second step of the wizard, you will need to assign teams to roles. You can do that by doing a drag & drop action for each team into the corresponding role. You need to assign at least one team with the _admin_ role.
  * The last step shows the summary of the new project: name, description, environment and the teams assigned to this project with their roles.

### View project's information

To view the information on a specific project:

* Go to the [projects setting page](https://app.brainboard.co/settings/projects).
*   Click on the `View details` option that appears when you click on the three horizontal dots button at the end of the row for a project.

    ![View project info](../.gitbook/assets/view-project-info.png)
* The information of the project is displayed:
  * Name of the project
  * Teams that have access to this project with their respective roles
  *   The environments of the project&#x20;

      <figure><img src="../.gitbook/assets/project-info.png" alt=""><figcaption></figcaption></figure>

### Edit project information

To edit the information on a project:

* Go to the [projects setting page](https://app.brainboard.co/settings/projects).
*   Click on the `Edit project details` option that appears when you click on the three dots button at the end of the row for a project.

    ![View project info](../.gitbook/assets/edit-project-info.png)
* You can then change the information about the project:
  * Name.
  * Description.
  * The environments that will be created.
* Click on the disk icon from the top left of the drawer to save the new information about the project.

### Edit project roles

To edit the teams & roles of a project:

* Go to the [projects setting page](https://app.brainboard.co/settings/projects).
*   Click on the `Assign roles` option that appears when you click on the three dots button at the end of the row for a project.

    ![Assign roles](../.gitbook/assets/assign-roles.png)
* Here you can update the teams per role. You can do that by doing a drag & drop action for each team into the corresponding role. You need to assign at least one team to any role to advance.
* Click on `Update` button to save the new information about the project.

### Delete project

To delete a project:

* Go to the [projects setting page](https://app.brainboard.co/settings/projects).
*   Click on the `Delete project` button on the line of the project. You need to hover the line to see the options:

    ![Create a project](../.gitbook/assets/delete-project.png)
* You'll be asked to confirm the deletion, if you confirm the project will be permanently deleted. The last project cannot be deleted, as your account needs at least one project.

### Project roles

Different roles can be granted to teams for the project.

Granting access to a team, give them also access to the environments and architectures hosted inside the project.

There are 4 default roles:

#### 1. Admin

The members of a team having the admin role can perform any action on the project, its environments, architectures, versions, and deployments.

#### 2. Designer

The members of a team having the designer role can perform any action as the admin team except modifying the project information or deleting it.

#### 3. Operator

The members of a team having the operator role can manage the deployments only, they cannot change the design of the infrastructure.

#### 4. Guest

The members of a guest team can only view the project, its architectures, and deployments. They cannot change anything.

### Project IAM reference

| Object                  | Action              | Project admin | Project designer | Project operator | Project guest |
| ----------------------- | ------------------- | ------------- | ---------------- | ---------------- | ------------- |
| Project                 | get                 | yes           | yes              | yes              | yes           |
| Project                 | update              | yes           | no               | no               | no            |
| Project                 | delete              | yes           | no               | no               | no            |
| Environment             | create              | yes           | yes              | no               | no            |
| Environment             | update              | yes           | yes              | no               | no            |
| Environment             | delete              | yes           | yes              | no               | no            |
| Architecture            | create              | yes           | yes              | no               | no            |
| Architecture            | list                | yes           | yes              | yes              | yes           |
| Architecture            | get                 | yes           | yes              | yes              | yes           |
| Architecture            | update              | yes           | yes              | no               | no            |
| Architecture            | clone               | yes           | yes              | no               | no            |
| Architecture            | delete              | yes           | yes              | no               | no            |
| Architecture:version    | create              | yes           | yes              | no               | no            |
| Architecture:version    | checkout            | yes           | yes              | no               | no            |
| Architecture:deployment | create              | yes           | yes              | yes              | no            |
| Architecture:deployment | get                 | yes           | yes              | yes              | yes           |
| Architecture:deployment | update              | yes           | yes              | yes              | no            |
| Architecture:deployment | delete              | yes           | yes              | yes              | no            |
| Architecture:deployment | View Terraform code | yes           | yes              | yes              | no            |
