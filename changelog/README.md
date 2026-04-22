---
icon: clock-rotate-left
---

# Changelog

### 2026.04.10 - Apr 22, 2026

#### 🎉 Features and Improvements

* Connector
  * You can now move standalone connectors directly in the design area, making diagram cleanup and layout adjustments much faster.

#### ✅ Bug Fixes

* Design area / diagram
  * We improved element layering and highlighting behavior so selected and highlighted items are displayed more clearly and predictably while editing.

***

### 2026.04.8 - Apr 21, 2026

#### 🎉 Features and Improvements

_No user-facing feature improvements were introduced in this patch release._

#### ✅ Bug Fixes

* Infrastructure as Code
  * Fixed expression handling so Terraform function-based values are preserved correctly instead of being saved as plain strings.
* Audit log
  * Added architecture version activity tracking so teams can better audit who created or switched versions.

#### 🤖 AI

_This feature is currently accessible via a_ [_waiting list_](https://brainboardco.notion.site/brainy-alpha-feedback-program)_._

* AI Chat
  * Improved the empty-architecture AI entry experience so the prompt overlay stays stable during first drag-and-drop actions.
  * Refined conversation controls so chat actions appear only when a conversation is active.
  * Fixed chat closing behavior so closing a conversation no longer closes the entire left panel.

***

### 2026.04.5 - Apr 17, 2026

#### 🎉 Features and Improvements

_No user-facing feature improvements were introduced in this patch release._

#### ✅ Bug Fixes

* Architecture Templates
  * Fixed template browsing so templates no longer disappear when users apply filters or search, making template discovery more reliable.
* RBAC/Permissions
  * Fixed organization member permission checks used to show or hide the members menu in organization settings.

***

### 2026.04.4 - Apr 16, 2026

#### 🎉 Features and Improvements

* Design area / diagram
  * Selecting a resource now automatically highlights its related nodes and connections, making dependency paths much easier to understand at a glance.
* Pipelines
  * Job output can now be expanded to an almost full-screen view so teams can review long deployment logs more comfortably.

#### ✅ Bug Fixes

* Design area / diagram
  * Fixed a collaboration issue where selection indicators could disappear when multiple users were editing the same architecture.
  * Panel layout changes in one browser instance no longer unexpectedly affect another open instance.
  * Connector rendering now stays stable during advanced selection/highlight flows, avoiding intermittent editing issues.
* Project selector / Architecture selector
  * Fixed hover behavior in architecture/project trees so contextual actions appear consistently, including quick navigation back to project home.
* Workflow & Pipelines
  * Creating a workflow from a template now automatically adds a unique name suffix so teams can clone templates faster without manual renaming.
  * Fixed sticky table header styling in pipeline views so scrolling content no longer bleeds through.
* Settings - Team
  * Member detail panels no longer auto-close while interacting, allowing smoother review and copy actions.
* Architecture Templates
  * Template browsing now relies on improved server-side loading and filtering, giving users a more consistent and responsive catalog experience.
* Resource Configurator - Warnings
  * Fixed false validation warnings for indexed references (for example array-style attribute access), reducing noise during configuration work.

#### 🤖 AI

_This feature is currently accessible via a_ [_waiting list_](https://brainboardco.notion.site/brainy-alpha-feedback-program)_._

* AI Chat
  * Resolved an issue that could send duplicate chat messages when users navigated quickly between views.
  * AI-generated README updates now appear in the README panel immediately without requiring a page refresh.

***

### 2026.04.3 - Apr 13, 2026

#### 🎉 Features and Improvements

* Design area / diagram
  * Restoring an older architecture version now asks for confirmation and includes a one-click undo option for safer rollback workflows.
  * Locked resources can no longer be moved accidentally, improving layout control for shared diagrams.
  * Dragging resources from the left panel now highlights target containers correctly, making placement clearer.
* CI/CD
  * Workflow names are now checked for uniqueness so teams can avoid confusion and conflicts when creating or updating automations.
* Code edition / Bidirectional
  * Editing a single resource from code now keeps related connections in sync, making bidirectional updates more reliable.
  * Provider settings now preserve raw values more accurately, improving compatibility when working with variables and dynamic expressions.
* Command palette (CMD/CTRL+K)
  * Global search now looks across all architectures, helping teams find workspaces faster beyond just recent items.

#### ✅ Bug Fixes

* Import from cloud provider
  * Cloud import now handles unexpected provider responses more safely to prevent import interruptions.
* Design area / diagram
  * Switching between architectures now correctly resets the right panel to the resource list for a smoother editing flow.
  * Guided tours no longer appear unexpectedly when the right panel is closed.
  * Reverting to stricter node validation helps prevent invalid diagram states during save and sync operations.
  * Color controls in the design area now behave more consistently when editing and resetting styles.
  * Resource rotation works correctly again, including smoother angle handling.
  * Duplicating a resource now correctly duplicates its attached Brainboard file data when applicable.
* One Action & CI/CD
  * Plan preflight now shows module names correctly for clearer validation feedback.
* Project selector / Architecture selector
  * The architecture selector opens faster, especially in larger workspaces.
  * Opening an environment from the architecture now closes the panel first for cleaner navigation.

#### 🤖 AI

_This feature is currently accessible via a_ [_waiting list_](https://brainboardco.notion.site/brainy-alpha-feedback-program)_._

* AI Chat
  * Empty architecture overlay now behave correctly while AI generation is running, preventing conflicting visuals when reopening architectures.

***

### 2026.04.1 - Apr 06, 2026

#### 🎉 Features and Improvements

* Settings
  * Form experiences were standardized across major workflows to provide more consistent input behavior and clearer validation feedback.
* Integration
  * Tooltip behavior was unified across the app for a more consistent and polished experience across settings, cards, and workflow screens.

#### ✅ Bug Fixes

* CI/CD
  * Slack pipeline notifications now run with correctly built commands, restoring successful message delivery for teams using Slack integrations.
* Design area / diagram
  * Tooltips and dropdown-style content now render correctly inside dialogs instead of appearing in the wrong layer or position.
* Import from cloud provider
  * Azure resource imports now handle ambiguous or unsupported mappings more gracefully, reducing import interruptions for Azure users.
* `brainboard_file`
  * `brainboard_file` operations now provide clearer, user-friendly error messages (such as file size limits or unavailable content) to simplify troubleshooting.

***

### 2026.03.14 - Mar 31, 2026

#### ✅ Bug Fixes

* Design area / diagram
  * We relaxed strict node validation checks so existing architectures with legacy diagram data continue to load and work reliably instead of being blocked.

***

### 2026.03.13 - Mar 31, 2026

#### ✅ Bug Fixes

* Topbar
  * Breadcrumb navigation is now a single, clearer action that opens the architecture selector, reducing confusion when switching context.
* Screenshot
  * Fixed an issue where text borders could appear in generated screenshots.
* Code edition/Bidirectional
  * Fixed a stability issue in cloud configuration path handling to prevent failures in specific diagram update scenarios.

***

### 2026.03.12 - Mar 27, 2026

#### ✅ Bug Fixes

* Leftbar
  * Restored the default leftbar width for users without AI chat enabled (private alpha), providing a more comfortable design workspace and bringing back the expected layout behavior.

***

### 2026.03.11 - Mar 26, 2026

#### ✅ Bug Fixes

* Node / Containers
  * Line and arrow shapes now validate correctly, so these diagram elements work more reliably in real architectures.
  * Text and other nodes now consistently respect minimum sizing rules, preventing save and rendering issues in edge-case layouts.

***

### 2026.03.10 - Mar 26, 2026

#### 🎉 Features and Improvements

* New architecture
  * The new architecture screen now prioritizes **Create from scratch** as the first option, making the most common starting path quicker to access.

#### ✅ Bug Fixes

* Import from cloud provider
  * Cloud import failures now display clear, dedicated error messages in the interface, helping teams diagnose issues and recover faster.

***

### 2026.03.9 - Mar 19, 2026

#### ✅ Bug Fixes

* Design area / diagram
  * Deleting nodes now reliably cleans up related connectors, preventing diagram inconsistencies during node removal workflows.
* Resource Configurator
  * Switching between modules now correctly keeps each module’s own card data, avoiding unintended overwrites when editing.

#### Notes

* The “Create with AI” option has been removed from the new architecture flow. Its successor will soon be released under alpha feature flag. Contact support team if you want to be in the Alpha waiting list.&#x20;

***

### 2026.03.8 - Mar 18, 2026

#### 🎉 Features and Improvements

* Design area / diagram
  * Architecture revision history is now more resilient by keeping a larger recent revision window (10), making rollback and recovery safer when users need to restore a previous working state.

#### ✅ Bug Fixes

* RBAC/Permissions
  * Permission policy initialization was stabilized to ensure access rules are created and updated more reliably, reducing risk of inconsistent authorization behavior across organizations and projects.

***

### 2026.03.7 - Mar 17, 2026

#### 🎉 Features and Improvements

* Import from git
  * Importing modules from Git now forwards Git credentials more reliably, making private module imports smoother for teams using secured repositories.
* Cloud providers (AWS, Azure, GCP)
  * Azure load balancer backend pool address parsing was improved, with better deduplication of discovered cloud resources for cleaner imports.

#### ✅ Bug Fixes

* Connector
  * Automatic connector diagram validation was disabled to prevent unnecessary validation interruptions during editing workflows.
* API
  * Endpoint validation and JSON patch path checks were strengthened for diagram, cloud configuration, and variable operations, improving request reliability and reducing invalid update errors.

***

### 2026.03.4 - Mar 09, 2026

#### ✅ Bug Fixes

* **Project selector / Architecture selector**
  * Fixed search state so the project selector no longer keeps stale search input after closing.
* **New Architecture - all Imports**
  * Simplified the import experience by removing unnecessary right-side header actions for a cleaner, more focused interface.
  * Fixed issues when architecture information was set during cloud provider import.
* **Variables/Locals/Output**
  * Fixed variable value display so scrolling is visible and values are easier to review.
  * Fixed the variables import tab by hiding an incorrect add button.
  * Improved variable synchronization reliability by clearing stale variable cache during code edition updates.
* **Infrastructure as Code /** **Identity Card**
  * Fixed preflight validation behavior on meta attributes to reduce false validation issues.
  * Improved exported infrastructure blocks by correctly including computed attributes, leading to more complete and reliable outputs.
* **RBAC/Permissions**
  * Fixed batch authorization handling for invalid resource IDs to improve access control reliability.

***

### 2026.03.3 - Mar 02, 2026

#### ✅ Bug Fixes

* **Import from cloud provider**
  * AWS import handling was improved to better manage EKS-related resources and large tagging scenarios, making cloud imports more robust for complex environments.
* **Leftbar**
  * Fixed drag-and-drop behavior in the left sidebar for a smoother and more consistent editing experience.
* **Node / Containers**
  * Fixed container color rendering so container nodes now consistently use their intended default colors.
* **Connector**
  * Fixed an issue where connectors could remain after related endpoint nodes were removed, keeping diagrams clean and accurate.

***

### 2026.02.4 - Feb 19, 2026

#### 🎉 Features and Improvements

* Connector
  * Terraform reference deletion prompts now include a close option, making it easier to back out of accidental connector changes.

#### ✅ Bug Fixes

* CI/CD
  * Workflow jobs now automatically use the latest plugin schema, so existing pipelines keep working when plugins schema evolve.
  * Brainboard worker image used for Terraform/Opentofu plugins now include Git support so workflows can reliably fetch modules from Git-based sources.
  * Clearing a Terraform/OpenTofu `-target` no longer breaks runs, as empty targets are now ignored instead of being sent to the CLI.
* Settings
  * Fixed a visual layout issue on the GitHub connection form so the page displays cleanly when adding a personal token.
* Resource configurator - TF Reference enrichment
  * Module references now correctly show their custom icons in reference displays and previews for easier identification.

***

### 2026.02.3 - Feb 18, 2026

#### 🎉 Features and Improvements

* CI/CD - Plugins
  * Runner jobs now automatically use the IaC tool and version configured on the architecture, reducing manual setup in pipelines.
  * Runner plugin execution is now streamlined around a single worker image, making plugin environments more consistent and easier to maintain.

#### ✅ Bug Fixes

* Integrations - Cloud provider
  * Cloud provider connection setup now starts on the correct wizard step, making it easier to create new credentials without confusion.
* Settings - Teams & Members
  * Team member details now load reliably and correctly display 2FA status for GraphQL-based setups.

***

### 2026.02.2 - Feb 09, 2026

#### ✅ Bug Fixes

* Code edition
  * Editing the generated code with a Module with a custom Git SSH sources now preserve existing the settings so you can remove or update parameters without unexpected resets.
* Design area / diagram
  * Clicking a connector anchor point no longer creates “ghost” connectors, reducing accidental connections during editing.
* Global
  * Environments indicators now use a clearer icon so they’re easier to distinguish from public visibility.
* Node / Containers
  * Deleting a node from the context menu now only removes it from the diagram.
* Resource configuration
  * Duplicating repeatable configuration blocks now works correctly without false “duplicate” conflicts.

***

### 2026.02.1 - Feb 03, 2026

#### ✅ Bug Fixes

* Git credentials
  * Fixed an issue where secret fields could not be fully cleared when editing Git connections, improving credential updates for existing setups.
* Topbar
  * Improved spacing and responsive behavior so key actions and tabs stay accessible on smaller screens.
* Variables/Locals/Output
  * Improved the Variables pages layout on small screens, including better menu highlighting and clearer empty-state positioning.
* Self hosted runners
  * Fixed missing “job starting” status messages in self-hosted runner logs so job progress is easier to track during execution.

***

### 2026.01.9 - Jan 29, 2026

#### 🎉 Features and Improvements

* Module
  * Module fields (ie module's variable) without an explicit type now automatically the default value to infer the type (e.g., boolean, number, list, map). The type is used in our Resource configuration form and in the code generation as well.

#### ✅ Bug Fixes

* Module
  * Custom-typed module's field are now generated correctly in Terraform without unwanted quotes, preventing invalid `true/false` values in output.
* Resource Configuration - Suggestion assistant
  * The `depends_on` field now stops at the resource level (no attribute selection), avoiding incorrect references and extra steps when defining dependencies.
  * The suggestion assistant dropdown no longer close unexpectedly when selecting resource/variable filters.

***

### 2026.01.8 - Jan 27, 2026

#### ✅ Bug Fixes

* Node / Containers
  * Improved the Node Options border controls so padding and selection styling display consistently.
* Architecture
  * Unsyncing an architecture now keeps your work intact by duplicating the diagram instead of reusing the shared one.
* Code edition
  * Nested configuration blocks now preserves the correct IDs, avoiding mismatches when blocks share the same order under different parents.
* Variables/Locals/Output
  * Bulk delete for Outputs now reliably removes the selected items.

***

### 2026.01.7 - Jan 22, 2026

#### ✅ Bug Fixes

* Settings
  * Fixed Project Settings loading issues for organizations with many projects by fetching only the needed project instead of an incomplete list.
* Node Right-Click Menu
  * Updated node menu labels and icons to make common actions clearer (e.g., omitting/adding nodes to code).
* Module Import - Git credentials
  * Improved module import credential handling so Git service and credentials are selected and saved more reliably.
* RBAC/Permissions
  * Clarified project creation permissions so roles display and behave more accurately in settings.
* Infrastructure as Code
  * Improved the Terraform file selector in the right pane so long file names are easier to pick and review.

***

### 2026.01.6 - Jan 20, 2026

#### 🎉 Features and Improvements

* Cloud providers Credentials (Azure)
  * Improved the Azure “Renew certificate” flow with clearer guidance, copy-to-clipboard for the App ID, and safer validation after download.
* Topbar
  * Updated the topbar experience and removed the “new topbar” feature flag so everyone gets the same improved navigation.

#### ✅ Bug Fixes

* Workflow
  * Fixed an issue that could cause errors when opening a workflow that doesn’t exist or isn’t accessible.
* CI/CD
  * Enhanced drift checks to support Terraform variable files and better control of the IaC runtime used during scans.
* Resource Configurator (Listing)
  * Fixed resource cards showing incorrect “\[object Object]” values by improving how complex values are displayed.
* Code edition
  * Fixed invalid parsing/generated code for certain arrays so Terraform plans no longer fail due to missing separators.

***

### 2026.01.5 - Jan 14, 2026

#### 🎉 Features and Improvements

* Project selector / Architecture selector
  * Added “Expand all / Collapse all” controls and shift-click shortcuts to quickly expand or collapse project and environment trees.
* General
  * Reduced the Brainboard web app download size to speed up loading, especially on slower networks.
  * Improved how the app detects and applies new versions so updates are more reliable.

#### ✅ Bug Fixes

* Design area / diagram
  * Fixed the multi-selection node menu so “Edit TF filename” is available when multiple nodes are selected.
* State management
  * Fixed Terraform/OpenTofu state imports in pipelines when variable values are provided via a `.tfvars` file.

***

### 2026.01.4 - Jan 13, 2026

#### 🎉 Features and Improvements

* Import from files
  * Added clearer guidance and validation so you’re prompted to upload `.tf` files before generating a diagram.
* New organization
  * All new organizations have OpenTofu as default binary execution

#### ✅ Bug Fixes

* Design area
  * Fixed missing node borders while dragging and dropping nodes in the design area.
  * Fixed the node context menu not opening reliably in the design area.
  * Improved timeout and error messaging so large-diagram actions fail more clearly and provide more actionable feedback.

***

### 2026.01.2 - Jan 12, 2026

#### 🎉 Features and Improvements

* Architecture selector
  * Projects and environments in the architecture selector now stay collapsed until you expand them, making navigation clearer and less cluttered.
  * The currently selected architecture is now highlighted more consistently in the selector.
* Design area / diagram
  * Resource cards now use a virtualized list for smoother scrolling and better performance on large architectures.
* Git credentials
  * Bitbucket connections now use an API token instead of a password for a more secure and modern authentication flow.
* Module
  * The Modules Catalog and module import experience have been refreshed for a more consistent UI and smoother workflows (including custom icons and improved dialogs).

#### ✅ Bug Fixes

* Infrastructure Management
  * Cloud configuration inheritance is now skipped safely when a referenced child node is missing, preventing errors in edge-case diagrams.
* CI/CD Plugins
  * The Checkov plugin now supports passing a repository identifier, improving scan context for teams running checks across multiple repos.

***

### 2026.01.01 - Jan 08, 2026

#### 🎉 Features and Improvements

* Design area / diagram
  * Introduced a unified, declarative node and resource menu with a global context menu, making right‑click actions consistent and easier to extend across the design area.
* Node / Containers
  * Updated node selection so clicking a node always selects it and opens the right configuration panel when appropriate, avoiding confusing partial selections.
  * Improved multi‑node alignment tools to work reliably on large selections, keeping nodes neatly aligned without layout jumps.
* Identity Card / Resource Configurator
  * Enhanced resource summaries with syntax‑highlighted tooltips for multiline or advanced values, helping users understand complex attributes without opening full editors.
* Architecture
  * Ensured architectures always keep an accurate cloud provider icon when diagrams change or are cloned, improving filtering, reporting, and provider‑specific behaviors.
* New architecture / Import from files / Restore
  * Replaced legacy file uploaders with a unified drag‑and‑drop component across variable imports, local file imports, and architecture restore, giving a consistent and more robust upload experience.
  * Relaxed overly strict invalid‑file handling so users can proceed as long as at least one valid file is present, reducing friction when importing from mixed folders.
* Cloud provider credentials
  * Added the ability to regenerate and download new Azure client certificates directly from the connections page, simplifying certificate rotation.

#### ✅ Bug Fixes

* Design area / diagram
  * Fixed a regression where the design area could feel sluggish when moving many nodes or connectors, especially in large architectures.
  * Corrected invisible hit‑areas on certain nodes so selection and dragging work reliably even when nodes have very thin strokes.
  * Resolved an issue where highlighted nodes and connectors were not always cleared correctly when closing the configurator, preventing “ghost” highlights.
* Connectors
  * Fixed connector label and endpoint moves that sometimes produced duplicate or invalid points, which could cause jagged or broken connector paths.
  * Corrected hover detection around nodes when dragging connector endpoints, so nearby nodes are highlighted accurately without false positives.
  * Ensured Terraform‑linked connectors update or detach their references correctly when endpoints move between resources, avoiding stale or broken references.
* Node / Containers
  * Fixed node option bar behavior so it no longer depends on the identity card state, ensuring options appear correctly whenever nodes are selected.
  * Addressed a bug where container toggling and icon‑only modes could leave nodes in inconsistent visual states.
* Identity Card / Resource Configurator
  * Fixed a focus issue in availability zone fields so the cursor reliably moves into the correct input after switching modes, speeding up form editing.
  * Resolved missing or stale form data when switching between resources in the configurator by resetting and unregistering fields correctly.
  * Corrected collapsible section defaults and persistence per resource type, so sections open and close predictably across sessions.
  * Removed unnecessary re‑renders in the configurator that could cause flickering or slowdowns when editing complex resources.
* Onboarding
  * Fixed a flickering issue in the onboarding form

