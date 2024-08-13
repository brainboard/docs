# IAM reference 🔑

Find below the complete reference of roles and permissions in Brainboard.

### Organization roles

| Object          | Action              | role: organization: owner | role: organization: admin | role: organization: billing | role: organization: member |
| --------------- | ------------------- | ------------------------- | ------------------------- | --------------------------- | -------------------------- |
| Organization    | get                 | yes                       | yes                       | yes                         | yes                        |
| Organization    | update              | yes                       | yes                       | no                          | no                         |
| Organization    | delete              | yes                       | no                        | no                          | no                         |
| Org:member      | invite              | yes                       | yes                       | no                          | no                         |
| Org:member      | list                | yes                       | yes                       | yes                         | yes                        |
| Org:member      | get                 | yes                       | yes                       | yes                         | yes                        |
| Org:member      | update              | yes                       | yes                       | no                          | no                         |
| Org:member      | delete              | yes                       | yes                       | no                          | no                         |
| Billing         | Not yet implemented | yes                       | no                        | yes                         | no                         |
| Team            | create              | yes                       | yes                       | no                          | yes                        |
| Team            | list                | yes                       | yes                       | no                          | yes                        |
| Team            | get                 | yes                       | yes                       | no                          | yes                        |
| Project         | create              | yes                       | yes                       | no                          | yes                        |
| Project         | list                | yes                       | yes                       | no                          | yes                        |
| Project         | get                 | yes                       | yes                       |                             |                            |
| Project         | update              | yes                       | yes                       |                             |                            |
| Project         | delete              | yes                       | yes                       |                             |                            |
| Environment     | create              | yes                       | yes                       |                             |                            |
| Environment     | update              | yes                       | yes                       |                             |                            |
| Environment     | delete              | yes                       | yes                       |                             |                            |
| Architecture    | create              | yes                       | yes                       |                             |                            |
| Architecture    | list                | yes                       | yes                       |                             |                            |
| Architecture    | get                 | yes                       | yes                       |                             |                            |
| Architecture    | update              | yes                       | yes                       |                             |                            |
| Architecture    | clone               | yes                       | yes                       |                             |                            |
| Architecture    | delete              | yes                       | yes                       |                             |                            |
| Arch:variables  | TODO                | yes                       | yes                       |                             |                            |
| Arch:version    | create              | yes                       | yes                       |                             |                            |
| Arch:version    | checkout            | yes                       | yes                       |                             |                            |
| Arch:deployment | create              | yes                       | yes                       |                             |                            |
| Arch:deployment | get                 | yes                       | yes                       |                             |                            |
| Arch:deployment | update              | yes                       | yes                       |                             |                            |
| Arch:deployment | delete              | yes                       | yes                       |                             |                            |
| Arch:deployment | View Terraform code | yes                       | yes                       |                             |                            |
| Credential      | create              | yes                       | yes                       |                             |                            |
| Credential      | list                | yes                       | yes                       |                             |                            |
| Credential      | get                 | yes                       | yes                       |                             |                            |
| Credential      | update              | yes                       | yes                       |                             |                            |
| Credential      | delete              | yes                       | yes                       |                             |                            |

### Team and project roles

| Object          | Action              | role: team: admin | role: team: member | role: project: admin | role: project: designer | role: project: operator | role: project: guest |
| --------------- | ------------------- | ----------------- | ------------------ | -------------------- | ----------------------- | ----------------------- | -------------------- |
| Team            | update              | yes               | no                 |                      |                         |                         |                      |
| Team            | delete              | yes               | no                 |                      |                         |                         |                      |
| Project         | get                 |                   |                    | yes                  | yes                     | yes                     | yes                  |
| Project         | update              |                   |                    | yes                  | no                      | no                      | no                   |
| Project         | delete              |                   |                    | yes                  | no                      | no                      | no                   |
| Environment     | create              |                   |                    | yes                  | yes                     | no                      | no                   |
| Environment     | update              |                   |                    | yes                  | yes                     | no                      | no                   |
| Environment     | delete              |                   |                    | yes                  | yes                     | no                      | no                   |
| Architecture    | create              |                   |                    | yes                  | yes                     | no                      | no                   |
| Architecture    | list                |                   |                    | yes                  | yes                     | yes                     | yes                  |
| Architecture    | get                 |                   |                    | yes                  | yes                     | yes                     | yes                  |
| Architecture    | update              |                   |                    | yes                  | yes                     | no                      | no                   |
| Architecture    | clone               |                   |                    | yes                  | yes                     | no                      | no                   |
| Architecture    | delete              |                   |                    | yes                  | yes                     | no                      | no                   |
| Arch:version    | create              |                   |                    | yes                  | yes                     | no                      | no                   |
| Arch:version    | checkout            |                   |                    | yes                  | yes                     | no                      | no                   |
| Arch:deployment | create              |                   |                    | yes                  | yes                     | yes                     | no                   |
| Arch:deployment | get                 |                   |                    | yes                  | yes                     | yes                     | yes                  |
| Arch:deployment | update              |                   |                    | yes                  | yes                     | yes                     | no                   |
| Arch:deployment | delete              |                   |                    | yes                  | yes                     | yes                     | no                   |
| Arch:deployment | View Terraform code |                   |                    | yes                  | yes                     | yes                     | no                   |
