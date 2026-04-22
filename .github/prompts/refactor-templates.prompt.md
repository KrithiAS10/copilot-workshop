---
name: refactor-templates
description: "Use when: refactoring templates into components or updating markup patterns"
---

Inputs
------

- `target_files` (required) — glob or list of template paths to change
- `goal` (required) — brief statement of desired outcome (e.g., "extract
  header into component and remove duplication")
- `constraints` — compatibility or visual constraints to preserve

Prompt
------

Produce a plan and patch suggestions to refactor the specified templates.
Output should include:

- High-level steps (1–4 bullets).
- Specific component names and example include statements.
- A compact diff-style patch suggestion for each changed file.

Example usage:

target_files: app/templates/*.html
goal: Extract repeated header into `components/site_header.html`
constraints: Keep existing CSS classes and view context unchanged
