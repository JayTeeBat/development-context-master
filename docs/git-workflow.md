# Git Workflow

## Default Model

Use trunk-based development with pull requests.

## Branching Rules

- `main` is the only long-lived integration branch
- work happens on short-lived branches
- use one branch per objective
- branch prefixes:
  - `feat/`
  - `fix/`
  - `refactor/`
  - `docs/`
  - `chore/`

## Parallel Collaboration

- prefer small PRs over long-lived branches
- use stacked PRs when a larger change needs sequencing
- rebase private branches frequently to reduce drift
- avoid multiple concurrent branches changing the same subsystem without
  coordination
- use feature flags or additive changes for incomplete work

## History Rules

- rebasing private branches is allowed
- rewriting shared branches is not allowed
- merge through reviewed PRs only
- cut releases from `main` with tags
