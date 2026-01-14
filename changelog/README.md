---
icon: clock-rotate-left
---

# Changelog



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

