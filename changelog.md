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

### 2025.02.4 - Feb 11, 2025

#### ✅ Bug Fixes

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

