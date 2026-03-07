# Python Profile

## Purpose

This is the first-class engineering profile for repositories built with Python.

## Required Toolchain

- `uv` for environment and dependency management
- `pre-commit` for local guardrails
- `ruff` for formatting and linting
- `ty` for type checking
- `pytest` for tests

## Baseline Quality Gates

Run from repository root:

1. `uv sync`
2. `uv run pre-commit run --all-files`
3. `uv run ruff format --check .`
4. `uv run ruff check .`
5. `uv run ty check`
6. `uv run pytest`

## Coding Standards

- Type production function signatures
- Type public APIs and configuration models
- Minimize `Any` and justify it when needed
- Keep I/O boundaries explicit
- Separate side effects from business logic
- Favor small modules with clear responsibilities
- Treat public interfaces as stable by default

## Testing Standards

- Logic changes require unit tests
- Boundary-crossing changes require integration tests
- Bug fixes require regression tests

## Packaging And Layout

- Use `src/` layout
- Configure toolchain in `pyproject.toml`
- Keep scripts out of the production package unless they are product entry
  points

## Documentation Standards

- Update README when setup or usage changes
- Add ADRs for significant architecture decisions
- Document durable workflows under `docs/`
