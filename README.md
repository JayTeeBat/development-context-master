# development-context-master

Baseline workspace development standards and operating policy.

## What This Repository Provides

This repository maintains a canonical development context document that can be used as the root policy for a multi-repo workspace.

Primary artifact:
- `DEVELOPMENT-CONTEXT.md`: workspace-wide workflow, engineering guidelines, tooling defaults, quality gates, documentation policy, and definition of done.

## Intended Usage

Use this repository when you want a single source of truth for how development should be performed across multiple repositories.

Typical use cases:
- Bootstrapping a new workspace with consistent engineering standards.
- Aligning agent and human contributors on shared workflow and quality expectations.
- Standardizing Python-heavy development with Astral tooling (`uv`, `ruff`, `ty`).

## Policy Model (Precedence)

The model is intentionally two-level:
1. Workspace baseline in `DEVELOPMENT-CONTEXT.md`.
2. Repository-specific overrides in each repo `AGENTS.md`.

Repository `AGENTS.md` can refine implementation details, but should not weaken workspace-level safety and security expectations.

## Quick Start

1. Keep `DEVELOPMENT-CONTEXT.md` at the workspace root.
2. Update the `Scope` section path to match your local workspace.
3. In each repository, add or update `AGENTS.md` with project-specific rules.
4. Ensure user-facing guidance lives in each repo `README.md`.
5. Add workflow diagrams as `.puml` files where process clarity is needed.

## Default Quality Gates

Unless a repository defines replacements in its `AGENTS.md`, run:

```bash
uv sync
ruff format --check .
ruff check .
ty check
pytest
```

## Maintenance Guidelines

- Keep `DEVELOPMENT-CONTEXT.md` concise, enforceable, and tool-accurate.
- Update this repository when workflow, tooling, or policy standards change.
- Treat changes as governance changes: document rationale clearly in commit/PR descriptions.

## Related Documentation Roles

- `AGENTS.md`: agent-facing operational instructions.
- `README.md`: user-facing usage and onboarding documentation.
- `.puml`: workflow/process diagrams.
