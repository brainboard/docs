# Roles

Different roles can be granted to teams for the project.

Granting access to a team, gives them also access to the environments and architectures hosted inside the project.

There are 4 roles:

#### 1. Admin

The members of a team having the admin role can perform any action on the project, its environments, architectures, versions, and deployments.

#### 2. Designer

The members of a team having the designer role can perform any action as the admin team except modifying the project information or deleting it.

#### 3. Operator

The members of a team having the operator role can manage the deployments only, the cannot change the design of the infrastructure.

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
