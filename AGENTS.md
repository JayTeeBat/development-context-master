# AGENTS.md Template

Use this file as a starting point for repository-level agent instructions.
Copy into a target repository as `AGENTS.md`, then replace placeholders.

## Purpose
This file defines agent-facing operating rules for this repository.
It refines workspace defaults from `DEVELOPMENT-CONTEXT.md` with repo-specific instructions.

## Scope
Applies to all agent work in this repository.

## Precedence
1. Safety/security constraints from workspace context are minimum requirements.
2. This repository `AGENTS.md` defines local implementation rules.
3. If a conflict exists, follow this file for repo behavior unless it weakens workspace safety/security standards.

## Repository Context
- Repository name: `<REPO_NAME>`
- Primary language(s): `<LANGUAGES>`
- Runtime/build system: `<RUNTIME_OR_BUILD_SYSTEM>`
- Key directories:
- Source: `<SRC_PATH>`
- Tests: `<TEST_PATH>`
- Docs: `<DOCS_PATH>`
- Entry points/services: `<ENTRYPOINTS>`

## Standard Workflow
1. Read this `AGENTS.md` first.
2. Implement the requested feature or change.
3. Run all repository quality gates.
4. Update documentation cleanly.
5. Commit only if all quality gates pass.

## Engineering Guidelines
- Design clean APIs with explicit boundaries.
- Prefer maintainable and extendable code.
- Minimize coupling and isolate responsibilities.
- Keep public interfaces stable unless a breaking change is approved.

## Toolchain Standards
- Python-heavy repositories should default to Astral tooling.
- Strong typing is expected across production code.
- Preferred tools: `uv`, `ruff`, `ty`.
- Repo-specific additions: `<ADDITIONAL_TOOLS>`

## Quality Gates
Run from repository root unless explicitly documented otherwise.

Default baseline:
1. `uv sync`
2. `ruff format --check .`
3. `ruff check .`
4. `ty check`
5. `pytest`

Repository overrides/additions:
1. `<CUSTOM_GATE_1>`
2. `<CUSTOM_GATE_2>`

## Testing Policy
- Logic changes require unit tests.
- API/integration/data-flow changes require integration tests where boundaries are crossed.
- Bug fixes require regression coverage.
- If a required test type is impractical, explain the rationale in PR notes.

## API Compatibility Rules
- Prefer backward-compatible changes by default.
- Breaking changes require migration notes and explicit version impact.
- Deprecations require documentation of replacement path before removal.

## Dependency And Versioning Policy
- Use pinned or constrained dependency versions as appropriate.
- Keep dependencies updated on a regular cadence.
- Validate major upgrades with compatibility review and tests.

## Security Baseline
- Never commit secrets, tokens, or credentials.
- Use approved secret management and environment configuration.
- Do not log sensitive data.
- Run security/static checks included in quality gates.

## Documentation Standards
- `README.md` is user-facing documentation.
- `AGENTS.md` is agent-facing operational guidance.
- Use `.puml` for workflow diagrams when process changes or complexity warrants it.

## Commit And PR Conventions
- Keep commits focused and scoped.
- Use clear commit messages that explain intent and impact.
- PR descriptions should include summary, testing evidence, and documentation impact.
- Do not merge with failing quality gates.

## Architecture Decision Records
- Create ADRs for major design decisions and tradeoffs.
- ADR content should include context, options, decision, and consequences.
- ADR location: `<ADR_PATH>`

## Definition Of Done
- Requested change is implemented.
- Quality gates pass.
- Relevant docs are updated (`README.md`, `AGENTS.md`, `.puml`, ADRs when needed).
- Change is ready to merge or committed per repository process.
