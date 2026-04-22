---
name: create-release
description: "Use when: preparing a release changelog and PR description for a new version"
---

Inputs
------

- `version` (required) — semantic version string, e.g. `v1.2.0`
- `highlights` — short summary bullets of user-facing changes
- `changes` — list of grouped changes (features, fixes, docs)
- `breaking_changes` — optional description of breaking changes
- `contributors` — optional list of contributor usernames

Prompt
------

Create a concise release summary and a GitHub PR description. Output:

1) A short release headline (1 line).
2) A Markdown-formatted changelog grouped by category (Features, Fixes,
   Documentation, Other).
3) A PR description that includes upgrade notes and a checklist.

Example usage (fill the fields and send to the agent):

version: v1.2.0
highlights:
- Added bingo board component customization
- Improved test coverage for game logic
changes:
Features:
- Add `bingo_board` component with responsive layout
Fixes:
- Fix off-by-one bug in `game_logic.start()`
breaking_changes: None
contributors: @alice, @bob
