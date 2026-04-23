---
description: >-
icon: clipboard-list
sidebar_label: "Release Notes"
sidebar_position: 3
---

# Release Notes

## Version 2.3.0

_Release Date: March 2026_

<table>
  <thead>
    <tr>
      <th>Compatibility</th>
      <th>Version</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Integrations Hub</td>
      <td>2.3.0</td>
    </tr>
  </tbody>
</table>

Introducing version 2.3.0 of the Integrations Hub installer, featuring newly added verification flows, updated scope authentication features, and system fixes for a smoother experience.

### What's New

* **Updated UIH Scope Authentication** – Upgraded the scope authentication mechanism for integrations and verified comprehensive compatibility (e.g., SharePoint integration).
* **System Log Fixes** – Resolved misconfigured info messages surrounding `AuthenticationProvider` beans to clean up system logs.
* **New Docker Based Installer** – The installer is now Docker image based without management scripts.

### Changes

* Includes underlying setup changes for future CI/CD and deployment enhancements.

### Documentation Enhancements

* **Domain Context & De-jargoning:** Introduced a centralized global `glossary.md` defining core technologies (Docker, Vault, Nginx) alongside inline explanatory hints across highly technical pages to dramatically lower the barrier of entry for new sysadmins.
* **Metadata Injection:** All documentation pages now contain frontmatter descriptions for native GitBook subtitle rendering and improved search indexing.
* **Style & Grammar Overhaul:** Executed a repository-wide copy-edit to standardize list punctuation, re-phrase complicated instructions, and modernize instruction sequences by minimizing rigid numerical lists in favor of block-based content flows.