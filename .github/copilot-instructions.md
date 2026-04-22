---
name: copilot-instructions
applyTo: "**"
description: |
  Workspace-level guidance for Copilot Chat agents. Provides project-specific
  conventions, discovery hints, and templates for creating file-level
  instructions, prompts, and skills. Keep this file short; link to docs.
---

Purpose
-------

This file provides high-level guidance the conversational agent should load
for general, cross-cutting decisions in this repository (how to run, test,
where important files live, and how to add more agent customizations).

Principles
----------

- Link, don't embed: prefer linking to tests, architecture notes, and long
  reference docs under `docs/` rather than copying them here.
- Small surface: keep descriptions short and search-friendly (use the
  "Use when:" pattern for triggers).
- Use `applyTo` globs for narrow instructions; avoid `applyTo: "**"` unless
  the guidance truly applies everywhere.

Quick start for contributors
----------------------------

- Run locally: `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`
- Tests: `uv run pytest`
- Lint: `uv run ruff check .`

Where to add agent customizations
---------------------------------

- Workspace instructions (this file): `.github/copilot-instructions.md`
- File or scoped instructions: `.github/instructions/*.instructions.md`
- Prompts: `.github/prompts/*.prompt.md` or the user's prompt folder
  (`{{VSCODE_USER_PROMPTS_FOLDER}}/`)
- Skills: `.github/skills/<name>/SKILL.md`

Template snippets
-----------------

Use a short YAML frontmatter and a concise `description` that includes
searchable trigger phrases. Example frontmatter:

---
name: my-instruction
applyTo: "src/api/**"
description: "Use when: editing API handlers; mentions endpoints, validation"
---

Examples of useful triggers
--------------------------

- "use when: running tests" — ensures test-related guidance appears
- "use when: refactoring templates" — surfaces UI conventions

Next suggestions (recommended small enhancements)
-----------------------------------------------

- Add a scoped instruction for frontend templates under
  `.github/instructions/templates.instructions.md` with `applyTo` set to
  `app/templates/**`.
- Add one or two `*.prompt.md` examples (e.g., `create-release.prompt.md`)
  to demonstrate parameterized prompts.

Contacts & references
---------------------

- CONTRIBUTING.md — contributor workflow
- README.md — project overview and commands
- docs/ — longer design and tutorial material
