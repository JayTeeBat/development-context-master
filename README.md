# repo-standard-kit

Portable development standards, starter kits, and bootstrap tooling for modern
software repositories.

## Purpose

This repository defines a practical operating model for building repositories
with humans and agents working together. It is designed to make good defaults
easy to adopt when creating a new repository and easy to reference when
maintaining an existing one.

This repository provides:

- normative documentation for repository development standards
- a required `AGENTS.md` contract for repository-level guidance
- a complete Python profile with quality gates and coding standards
- a trunk-based collaboration workflow for parallel development
- a standard Python repository layout
- starter-kit assets for new repositories
- a thin bootstrap tool for generating a new repository from the starter kit
- a JavaScript/TypeScript profile scaffold for later expansion

## What Is Normative

The normative source documents are:

- `docs/repo-standard.md`
- `docs/agent-operating-model.md`
- `docs/git-workflow.md`
- `docs/repo-layout.md`
- `docs/bootstrap-workflow.md`
- `profiles/python.md`

Templates and starter kits implement those standards, but the documents above
define the intent and rules.

## Repository Layout

- `docs/`: standards and operating guidance
- `profiles/`: language or repo-type specific standards
- `templates/`: reusable templates for repo-level files
- `starter-kits/`: copyable repository skeletons
- `src/repo_standard/`: packaged bootstrap implementation
- `examples/`: filled examples showing the standard in practice

## Bootstrap A New Python Repository

The recommended workflow is:

1. Create an empty target repository or working directory.
2. Run the bootstrap tool:

```bash
uv run repo-init \
  --profile python \
  --repo-name my-service \
  --package-name my_service \
  --description "Short repo purpose" \
  --output-dir ../my-service
```

3. Review the generated `AGENTS.md` and `README.md`.
4. Run the quality gates in the generated repository.
5. Make the initial commit on `main`.

Do not clone this standards repository as the starting point for a product
repository. Generate or template the target repository separately.

## Current Profiles

- `python`: first-class, complete, and opinionated
- `javascript-typescript`: scaffold only for future expansion

## Adoption Paths

Use this repository in one of two ways:

- New repository: bootstrap from `starter-kits/python/` via `repo-init`
- Existing repository: adapt the repo to match the standard and populate
  `AGENTS.md` using `templates/AGENTS.md`

## Design Principles

- Portable: no workspace-specific filesystem assumptions
- Practical: exact commands and concrete file layouts, not abstract policy only
- Collaborative: explicit human and agent responsibility boundaries
- Typed: strong typing expectations for Python code
- Small-batch: trunk-based PR workflow for parallel work
