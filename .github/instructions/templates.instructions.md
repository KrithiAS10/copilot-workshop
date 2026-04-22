---
name: templates-instructions
applyTo: "app/templates/**"
description: "Use when: editing Jinja2 templates, adding components, or changing layout/design conventions in `app/templates/`"
---

Quick purpose
-------------

Guidance for working with the project's Jinja2 templates and UI components.

Conventions
-----------

- Templates live under `app/templates/` and reusable fragments live in
  `app/templates/components/`.
- Keep templates small and composable: extract repeated blocks into a
  component and include via `{% include 'components/...' %}`.
- Use the existing CSS utilities and classes in `static/css/app.css`.
- Prefer semantic HTML and accessibility-friendly markers (roles/aria-*).

Common tasks
------------

- Adding a new component: create `app/templates/components/<name>.html`,
  add include usage in the parent template, and update any view that
  renders that template if context variables change.
- Refactoring: run the local dev server and visually verify changes.

Style and patterns
------------------

- Use Jinja2 control structures sparingly in templates; complex logic
  belongs in the view or helper functions (see `app/game_service.py`).
- Prefer passing explicit variables; avoid relying on global context.

Do not
------

- Do not embed large JS snippets directly in templates; put them in
  `static/js/` and import instead.
- Do not duplicate markup that should be a component.

References
----------

- CSS utilities and styling guidance: [docs/styles.css](docs/styles.css)
- Example components: `app/templates/components/bingo_board.html`
