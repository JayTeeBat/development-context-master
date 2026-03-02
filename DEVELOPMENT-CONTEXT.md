# Development Context

## Purpose
This document defines workspace-wide development context and engineering operating standards for all work under `/home/thomazo/dev`.

## Scope
These standards apply to all repositories in this workspace unless a repository-level `AGENTS.md` explicitly overrides them.

## Standard Workflow
1. Read `AGENTS.md` first.
2. Implement the requested feature or change.
3. Run all required quality gates.
4. Update documentation cleanly.
5. Commit only if all quality gates pass.

## Engineering Guidelines
- Design clean APIs with clear boundaries.
- Prioritize maintainable implementations.
- Favor extendable architecture and low coupling.

## Toolchain Standards
- Default assumption: Python-heavy repositories.
- Strong typing is expected across the codebase.
- Use Astral tooling by default: `uv`, `ruff`, and `ty`.

## Quality Gates (Default Commands)
Run these commands from the repository root unless that repository's `AGENTS.md` defines replacements:
1. `uv sync`
2. `ruff format --check .`
3. `ruff check .`
4. `ty check`
5. `pytest`

## Repository Override Policy
- Repository-level `AGENTS.md` may refine or extend these defaults when needed for local architecture and tooling.
- Workspace-level safety and security expectations are minimum standards and must not be weakened by repo overrides.
- If repo guidance conflicts with this file, follow repo `AGENTS.md` for implementation details and this file for shared baseline principles.

## Testing Policy
- Logic changes require unit tests.
- API, integration, or data-flow changes require integration tests when boundaries are involved.
- Bug fixes require a regression test that fails before the fix and passes after it.
- If a required test type is not practical, document the reason in the change notes.

## API Compatibility Rules
- Prefer backward-compatible changes for existing interfaces.
- Breaking changes require explicit versioning impact notes and migration guidance in docs.
- Deprecations should be announced in docs before removal, with a clear replacement path.

## Dependency And Versioning Policy
- Prefer pinned or constrained dependency versions appropriate to each repository's package management strategy.
- Keep dependencies current with regular maintenance updates.
- Major version upgrades require a short compatibility review and test validation before merge.

## Security Baseline
- Never commit secrets, tokens, or credentials.
- Use environment variables or approved secret-management paths for sensitive values.
- Avoid logging sensitive data (credentials, tokens, PII, production identifiers).
- Run dependency and static checks included in repository quality gates.

## Commit And PR Conventions
- Use clear, scoped commit messages that describe intent and impact.
- Keep commits focused and logically grouped.
- PR descriptions should include: summary, testing evidence, and documentation impact.
- Do not merge with failing quality gates.

## Architecture Decision Records
- Create an ADR for significant architectural decisions, major tradeoffs, or breaking design shifts.
- ADRs should capture context, options considered, decision, and consequences.
- Store ADRs in the repository's documented architecture/docs location.

## Documentation Standards
- `AGENTS.md` is agent-facing operational guidance.
- `README.md` is user-facing documentation.
- Use `.puml` files to document workflows when needed.

## Definition Of Done
- The requested change is implemented.
- Quality gates pass.
- Relevant documentation is updated (`README.md`, `AGENTS.md`, and workflow `.puml` files when applicable).
- The change is committed.
