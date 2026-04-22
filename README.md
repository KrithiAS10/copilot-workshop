🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

# Soc Ops — Social Bingo for Mixers

**Development checklist (required before PR):**

- Lint: `uv run ruff check .`
- Test: `uv run pytest`
- Run/build: `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`

Soc Ops is a compact Social Bingo web app for in-person mixers — match traits, get five in a row, start conversations.
---


**Highlights**
- Compact codebase: logic in `app/`, templates in `app/templates/`, assets in `static/`.
- Workshop material and tutorials in `workshop/` and `docs/`.
- Tests in `tests/` and linting via `ruff`.

Quickstart (condensed)

```bash
python -m venv .venv
source .venv/bin/activate
uv run pip install -e .[dev]
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Open http://localhost:8000 to try the app.

Explore: `app/game_logic.py`, `app/game_service.py`, `app/templates/components/`.

Contribute: see `CONTRIBUTING.md`. License: `LICENSE`.

