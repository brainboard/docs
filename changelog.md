---
icon: clock-rotate-left
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
---

# Changelog

### 2025.04.10 - Apr 17, 2025

#### 🎉 Features and Improvements

* Integrations - Cloud provider connection
  * Enhanced AWS assume role creation instructions.
* Import from Cloud provider
  * Added support of some AWS Cognito TF resources: `aws_cognito_user_pool` & `aws_cognito_identity_pool`
* Code Edition/Bidirectional
  * Enabled updates to `terraform.tfvars` file
  * Updated graphics via bidirectional synchronization when the architecture diagram is empty.

#### ✅ Bug Fixes

* Identity Card
  * Automatically load the selected cloud provider version when opening the identity card to ensure attributes are properly re-fetched.
* Node / Containers
  * Corrected node metadata region updates from bidirectional synchronization to ensure accurate data representation.
* New architecture - Git import
  * Fixed import of Terraform modules by checking if the module exists in currently imported modules.
  * Automatically select Git credentials if only one option is available, simplifying the setup process.
* CI/CD Designer
  * Resolved double scrolling issue in the CI/CD workflow preview for a more seamless navigation.

***

### 2025.04.9 - Apr 16, 2025

#### 🎉 Features and Improvements

* Git Configuration
  * Automatically set the pull request settings when creating a new architecture via git import, streamlining the setup process.
* Code edition - User Interface
  * Refactored the handling of editor modes in the design area to prevent losing unsaved changes, providing a smoother user experience when the page is refocused.

#### ✅ Bug Fixes

* Terraform Pane
  * Enhanced the Terraform code editor by adjusting the height of the pane for better visual alignment with the future topbar redesign.
* Code edition - locals & variable
  * Enhanced the code parsing process to skip variable or local deletion if they are edited from a different file, ensuring data integrity.
* Terraform Git Module
  * Corrected the handling of Terraform git module versions during import to ensure the correct version is always used.
* Identity Card
  * Fixed a spacing issue in the search functionality, affecting users who frequently use the search feature within the Identity Card.

***

### 2025.04.8 - Apr 15, 2025

#### ✅ Bug Fixes

* Code edition
  * Improved marker hooks and subscription handling for better performance and reliability in bidirectional editing.
  * Enhanced Terraform code import by using architecture provider versions, ensuring compatibility and reducing errors.
* New architecture
  * Resolved crashes at the last step when creating new architectures from the topbar or project selector, enhancing stability for users transitioning between architectures.

\


***

### 2025.04.7 - Apr 15, 2025

#### ✅ Bug Fixes

* Import from Git
  * Fixed search functionality when listing Bitbucket repositories by updating the library and modifying API calls.
  * Updated the interface for a cleaner layout and better visual hierarchy.

***

### 2025.04.6 - Apr 14, 2025

#### ✅ Bug Fixes

* Architecture
  * Enhanced the architecture creation process to prevent mismatches between environments and projects, ensuring data integrity.
* Git Configuration
  * Updated error handling in the Git plugin for better response management.
* Global
  * Prevented unnecessary page refresh during token refreshes, enhancing performance.

***

### 2025.04.4 - Apr 07, 2025

#### ✅ Bug Fixes

* Git Configuration
  * Resolved issues in the migration command to ensure it correctly filters modules with valid credentials.
* Identity Card
  * Improved error notification behavior for ID card fetch failures, ensuring notifications are only shown when opening the ID card, reducing unnecessary alerts.
* RBAC
  * Fixed the default `Admin` role adding `get` and `list` permissions to `User credentials`, enhancing security and reliability.

***

### 2025.04.3 - Apr 07, 2025

#### 🎉 Features and Improvements

* Git Connections & Pull request configuration

<figure><img src=".gitbook/assets/1r3i2FEbBRc584U0.png" alt=""><figcaption><p>Integrations > Git connections</p></figcaption></figure>

<figure><img src=".gitbook/assets/FMdlaAIQbRHVdsDK.png" alt=""><figcaption><p>Architecture Settings > Pull request configuration</p></figcaption></figure>

#### ✅ Bug Fixes

* Identity Card
  * Prevented the Identity Card from closing when the autocomplete is open, ensuring smoother user interactions.

***

### 2025.04.2 - Apr 03, 2025

#### 🎉 Features and Improvements

* Homepage
  * Added a 'Projects' tab to the homepage, allowing users to view and manage projects & architecture directly from the main interface.

<figure><img src=".gitbook/assets/tyyZstmDpGFDAtcX.png" alt=""><figcaption><p>Homepage - Projects &#x26; Architectures</p></figcaption></figure>

#### ✅ Bug Fixes

* Connector
  * Resolved issues with connector paths breaking when moving handlers, ensuring smoother and more reliable diagram adjustments.

***

### 2025.04.1 - Apr 02, 2025

#### ✅ Bug Fixes

* Pipelines - One Actions
  * Send pipeline status update events when creating a pending pipeline, improving real-time notifications and switch to One-Action job's output.
* Pull Request in CI/CD
  * Added support for custom commit messages in pull requests, allowing for more personalized and descriptive commit histories.

***

### 2025.03.11 - Mar 31, 2025

#### 🎉 Features and Improvements

* SSO
  * Enhanced user role assignment using claims for organization roles.

#### ✅ Bug Fixes

* Identity Card
  * Enhanced input focus handling to prevent unexpected closures.
  * Fixed input focus handling to prevent unexpected closures.
* Variables/Locals/Output
  * Improved handling of multi-line descriptions for local variables, ensuring correct formatting.
  * Addressed variable suggestion issues, ensuring variables appear promptly in the list.
* Diagram
  * Only normalized resource names to lowercase for modules, improving consistency.

***

### 2025.03.10 - Mar 24, 2025

#### 🎉 Features and Improvements

* Workflow
  * Introduced a cancel job functionality, allowing users to stop ongoing tasks with ease.

#### ✅ Bug Fixes

* Import from Cloud Provider
  * Enhanced import parser to clean redundant connectors (connectors from a resource to a parent container), ensuring better diagram generation.
  * Fixed issues with Azure certificate credential handling during cloud provider import, ensuring smoother integration for Azure users.
* Infrastructure as Code
  * Improved parsing by quoting block attribute keys that start with "--" ensuring better compatibility and error handling.

***

### 2025.03.9 - Mar 20, 2025

#### 🎉 Features and Improvements

* Design Area / Diagram
  * Enhanced visual feedback during node resizing for a smoother design experience.
* Home Page - Architecture Templates
  * Added homepage templates with new components and design adjustments for a more intuitive user experience.
* Settings
  * Refactored Terraform backend settings to use credentials, improving backend management.

***

### 2025.03.8 - Mar 13, 2025

#### 🎉  Features and Improvements

* Architecture Templates
  * Introduced a new feature for creating architectures using templates, enhancing the setup process with updated components and configurations.

#### ✅ Bug Fixes

* Code edition
  * Improved variable scope management during bidirectional imports, ensuring accurate scope handling and reducing unnecessary filtering.
* Templates
  * Fixed an issue where the modal would close unexpectedly when sorting, improving user interaction by preventing accidental closures.

***

### 2025.03.7 - Mar 12, 2025

#### ✅ Bug Fixes

* RBAC
  * Fixed the issue where role status remained in a loading state when enabling or disabling multiple roles.
* Containers
  * Corrected the bug where resizing a container smaller did not remove its children, preventing duplicate children.

***

### 2025.03.6 - Mar 11, 2025

#### 🎉 Features and Improvements

* Design Area / Diagram
  * Introduced dynamic visual indicators for node parentship changes during movement, enhancing the design experience.
  * Adding text overflow for container titles, ensuring better readability
* Global
  * Improved text overflow handling, ensuring better display of long text.

#### ✅ Bug Fixes

* Connector
  * Fixed the positioning of the Connector Options Bar to ensure it displays correctly relative to the selected connector part.
* Node / Containers
  * Prevented the display of container connector anchors when multiple nodes are selected, ensuring clarity in node selection.
* Cloud connections
  * Corrected the file type restrictions for Google and OCI credentials, ensuring users upload the correct file formats.

***

### 2025.03.5 - Mar 10, 2025

#### 🎉 Features and Improvements

* Design Area / Diagram - Connectors
  * Added offsets to container connector anchor points, improving the accuracy and visual alignment of connections.
* New architecture - all imports
  * Fixed the default style of diagrams created via import to maintain visual consistency.
* Settings
  * Unified the UI across all settings pages for a more consistent user experience.
* Readme
  * Automatically opens the README file in preview mode if it contains content, streamlining the review process.

#### ✅ Bug Fixes

* Git Configuration - Github
  * Fixed the oauth2 route forgotten during settings refactoring, improving flexibility in Git configurations.
* Authentication
  * Corrected the logout functionality, ensuring users can log out without issues.
* Home Page
  * Added missing status badges for recent deployments, providing clearer status updates.
* Design area
  * Prevented code omissions in the node contextual menu for non-TF resources (icons or logos).

***

### 2025.03.4 - Mar 07, 2025

#### 🎉 Features and Improvements

* New version popup
  * Enhanced the design of the new version banner for a more modern look.
* Diagram Generation (Import)
  * Fixed diagram node clustering to improve the accuracy of node placement and connections.
* Settings
  * Updated settings breadcrumbs to align with new identifiers for improved navigation.

#### ✅ Bug Fixes

* Project / Environment / Architecture
  * Architectures are now automatically deleted when environments are removed, streamlining project management.
* Git Configuration
  * Resolved an issue where Git credentials were not loading preventing user to import from Git when they start from the home page, ensuring smoother access.
* Settings
  * Corrected the redirect link in settings documentation to point to the correct page.
  * Fixed the minimum width of text fields in settings for better UI consistency.

***

### 2025.03.3 - Mar 06, 2025

#### 🎉 Features and Improvements

* Settings
  *   New Settings engine with a hierarchical structure that follows this inheritance pattern:

      **Organization → Project → Environment → Architecture**
  * Documentation available here: [overview.md](settings/overview.md "mention")
  * We will continue to migrate our settings (Remote backend, Git configuration, ...) to this new engine in the coming weeks.

<figure><img src=".gitbook/assets/bT0Jy0CqYXSeCzgY.png" alt=""><figcaption><p>Organization Setting page</p></figcaption></figure>

#### ✅ Bug Fixes

* Architecture
  * Fixed clone architecture functionality to support variable values of any type (including list/array).
* One-action
  * Introduced GraphQL subscription for real-time pipeline status updates, enhancing performance.

***

### 2025.03.2 - Mar 04, 2025

#### ✅ Bug Fixes

* New Architecture
  * Fixed issues with architecture creation by adding template selection and improving project/environment data handling.

***

### 2025.03.1 - Mar 03, 2025

#### 🎉 Features and Improvements

* Global
  * Introduced a new `Time` component for consistent date formatting across the platform.

#### ✅ Bug Fixes

* New architecture - Import from Cloud provider
  * Updated import cloud provider flow to prevent INVALID\_BODY error message, improving the architecture creation process.
* Home page - Recent deployments
  * Added a 'warning' status to deployment status mappings for better status visibility.
* Leftbar
  * Fixed the visibility issue when adding or pinning a module, ensuring all modules are displayed correctly.
* Settings - Projects
  * Resolved the "View details" option in the project list to ensure dropdowns close correctly after selection.
* Architecture Templates
  * Fixed the sync architecture modal to ensure it updates correctly with project data changes.

***

### 2025.02.11 - Feb 27, 2025

#### 🎉 Features and Improvements

* CI/CD - Plugin
  * MS Teams URL validation to include new webhook URL format, ensuring more robust integrations.
* Public API
  * Added VersionArchitecture endpoint to the public API documentation for better version management.
* New version notification
  * Enhanced the "New version available" component for better update notifications.

#### ✅ Bug Fixes

* Architecture
  * Prevented architecture creation if required fields are not filled, ensuring data integrity.
* Design Area
  * Fixed icons rendering issue on Firefox, ensuring a better diagram visualization on all supported browsers.
* Home Page
  * Added trial check in billing handler to correctly process trial subscriptions.
* Node configuration / Identity Card
  * Updated Identity Card component to show the cursor only on the drag handle, enhancing usability.

***

### 2025.02.10 - Feb 19, 2025

#### 🎉 Features and Improvements

* Design Area - Node
  * Enhanced context menu (right-click) for better user interaction.
  * Added state actions (import or delete from state) to the new contextual menu, enhancing Terraform state management and UI interactions.
* Text Node
  * Introduced Markdown support for text nodes, allowing for richer text formatting.

#### ✅ Bug Fixes

* Identity Card
  * Maintains focus on the Identity card during search for a smoother user experience.
* Design Area / Diagram
  * Fixed the Terraform filename selector by adding search functionality and improving dropdown styles.
* CICD Plugins
  * Removed Microsoft Teams URL regex validation to support new webhook URL format.
* Infrastructure Management
  * Skipped decreasing license user count when removing a member with a pending invitation, ensuring accurate license management.

***

### 2025.02.9 - Feb 14, 2025

#### 🎉 Features and Improvements

* Pull Request
  * Refactored the pull request user experience for a more intuitive workflow.

#### ✅ Bug Fixes

* Licensing
  * Resolved licensing issues by removing outdated billing plan references, ensuring compliance and smoother user management.
* Import from Files
  * Corrected file upload validation to accurately handle invalid extensions, improving file import reliability.
* Code edition
  * Added support for GCP region parsing, enhancing the accuracy of resource metadata.

***

### 2025.02.4 - Feb 11, 2025

#### ✅ Bug Fixes

* Architecture creation
  * Improved the summary view UX preventing the user to be softlocked selecting the project/environment where the architecture will be created.
* Screenshot / Export architecture as diagram
  * Screenshot in PRs, manual export are both resolved and working again.
* Node / Containers
  * Improved node action handling by reverting nodes to previous positions on failure and displaying error notifications.

***

### 2025.02.3 - Feb 07, 2025

#### ✅ Bug Fixes

* Import from cloud providers
  * Fixed the final import modal UI, improving error display and overall layout for a smoother user interaction.
* Git Configuration
  * Use user's input for the 'Source branch prefix' configuration
* Variables
  * Put back the 'Return to design area' for the few users that have access to the private alpha of Home page

\


***

### 2025.02.2 - Feb 05, 2025

#### ✅ Bug Fixes

* Import from Git&#x20;
  * Enhanced import functionality by using registry credentials for module imports
  * Improved error message to provide all details
* Git Configuration / Pull request
  * Updated GitLab integration to ensure repositories appear in PR searches, enhancing Git settings management.
  * Improved UI and modal handling in Git settings and pull request components, fixing layout issues.
* Design Area
  * Resolved issue where node selection was cleared when a text node was open, ensuring consistent selection behavior.

***

### 2025.02.1 - Feb 03, 2025

#### 🎉 Features and Improvements

*   Leftbar - Custom icons\


    * Introduced custom icon management, allowing users to add, edit, and delete icons for a personalized experience.

    <figure><img src=".gitbook/assets/yvtxOOo0rXaAtvV4.png" alt=""><figcaption></figcaption></figure>
*   Home Page \[Private access]

    <figure><img src=".gitbook/assets/thWeVj7zP5skt5zm.png" alt=""><figcaption><p>New home page</p></figcaption></figure>

    * Launched a new homepage with recent architectures, deployments, and activities
    * Reach out to the support team to get access to it

#### ✅ Bug Fixes

* Git Configuration
  * Resolved an issue where the incorrect version of a Terraform module was used during refresh, ensuring accurate module management.

***

### 2025.01.8 - Jan 31, 2025

#### 🎉 Features and Improvements

* Leftbar
  * Introduced the ability to expand and collapse the Leftbar and Terraform code panels via shortcuts `[` or `]`, enhancing user navigation and interface customization.

#### ✅ Bug Fixes

* Git Configuration
  * Implemented pagination for listing Git repositories, ensuring efficient loading and management of large repository lists.

***

### 2025.01.7 - Jan 30, 2025

#### 🎉 Features and Improvements

* Import files/git/modules
  * Added custom error messages for module variable parsing failures, enhancing error clarity and debugging.
* CICD: Architecture Version Plugin
  * Added success and error messages, improving user feedback and error handling.

#### ✅ Bug Fixes

* Git Configuration
  * Fixed handling of excluded files in Git pull requests within CI/CD jobs, ensuring correct file management.
  * Simplified Git settings submission logic, removing redundant functions for a cleaner user experience.

***

### 2025.01.6 - Jan 29, 2025

#### 🎉 Features and Improvements

* Design area
  *   Enhanced node inheritance, parenting, resize, and movement logic for more intuitive design interactions.\
      Inheritance and parent <> child relation will be triggered when you resize a container over nodes/containers.\


      <figure><img src=".gitbook/assets/Resize.gif" alt=""><figcaption></figcaption></figure>
* CI/CD Plugin
  * Introduced a new architecture version plugin to streamline version management.
* Identity Card & Terraform
  * Added support for boolean and ternary expressions, improving logic handling in configurations.
* API
  * Added API base URL display and documentation link to personal access token settings for easier API integration.

#### ✅ Bug Fixes

* Git Configuration
  * Re-fetch Git configuration when switching to another architecture within CI/CD workflow.
* Project Selector / Architecture Selector
  * Resolved crashes in the project selector, ensuring stability for users without assigned projects or architectures.

***

### 2025.01.5 - Jan 23, 2025

#### 🎉 Features and Improvements

* Connectors
  * Introduced animation options for connector lines and circles, allowing for a more dynamic and visually appealing design experience.
* CI/CD Plugins
  * Added the Trivy plugin, enhancing security scanning capabilities within CI/CD workflows.
* Import from Files
  * Implemented error handling for duplicate Terraform blocks during import, providing clear feedback to users.

#### ✅ Bug Fixes

* Readme
  * Enhanced the markdown editor with a switch between edit and preview modes, improving user experience when editing documents.
* Architecture Selector
  * Fixed an issue when updating the current architecture, ensuring users receive notifications if the architecture doesn't exist anymore.
  * The project selector now unfolds automatically, streamlining navigation and project management.

***

### 2025.01.4 - Jan 22, 2025

#### 🎉 Features and Improvements

* Synced architectures
  * Created architecture revisions for all synced architectures, ensuring up-to-date versions.
* CI/CD
  * Added a scrollbar to the CI/CD workflow view in pipeline details for improved navigation.

#### ✅ Bug Fixes

* Architecture selector
  * Fixed an issue where the architecture list remained empty when the last search did not match any record, ensuring accurate search results.
  * Prevented crashes if the current architecture was deleted, enhancing stability.
* Import from Cloud Provider
  * Created Terraform variables for empty required password attributes during cloud import, improving import accuracy.

***

### 2025.01.3 - Jan 16, 2025

#### 🎉 Features and Improvements

* Plugins
  * Introduced environment variable support for the Wiz plugin, enhancing configuration flexibility.

#### ✅ Bug Fixes

* Import from Cloud Provider
  * Corrected the error message when attempting to create an import with an existing name, ensuring clarity for users.
* Team Management
  * Resolved an issue with the click outside functionality when adding team members, improving user interaction and experience.

***

### 2025.01.2 - Jan 16, 2025

#### 🎉 Features and Improvements

* Design Area / Diagram
  * Revamped the Design Area Options Bar for a more intuitive user experience.
* Code edition (bidirectional)
  * Improved node creation order logic for better resource management.
* Import from Cloud
  * Added support for fetching Azure nested cloud resources by CloudID and Terraform Type like NSG subnet association (`azurerm_subnet_network_security_group_association` )

#### ✅ Bug Fixes

* Leftbar
  * Fixed broken shapes, logos, and icons when searching, improving the user interface for all users.
* Screenshot
  * Resolved issues with screenshots breaking when using custom icons or text.
* Import from Cloud Provider
  * Fixed import view issues and infinite table rendering for a smoother import experience.

***

### 2025.01.1 - Jan 07, 2025

#### 🎉 Features and Improvements

* Code Edition (Bidirectional) & Connector
  * Enabled bidirectional parsing and management of connectors for better integration and functionality.
  * Enhanced HCL parser to support bidirectional parsing of connectors, improving code management.
* Import from Cloud Provider
  * Ensured Azure resources' terraformID includes the correct case-sensitive resource group for accurate deployments.
  * Fixed JSON format issues during import to ensure correct data handling and display.

