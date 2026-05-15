# AGENTS

## Dev checklist
- `uv sync`
- `uv run ruff check .`
- `uv run pytest`
- `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`

## Purpose
Workshop app with FastAPI + Jinja2 + HTMX for a social bingo game.

## Key commands
- `uv sync` — sync dependencies.
- `uv run pytest` — run tests.
- `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000` — start development server.
- `uv run ruff check .` — lint code.

## Structure
- `app/` — backend, templates, static assets.
- `tests/` — API and game logic tests.
- `workshop/` — lab guide content.

## Conventions
- Use `app/static/css/app.css` utilities; avoid new CSS frameworks.
- Keep HTMX partial rendering in `app/templates/components/`.
- Prefer editing `app/` over `.solutions/` unless working on examples.
- Maintain session-based state in `app/game_service.py` and bingo rules in `app/game_logic.py`.

## Useful files
- `README.md` — project overview and lab guide links.
- `pyproject.toml` — dependencies and scripts.
- `.github/instructions/` — frontend and CSS conventions.
