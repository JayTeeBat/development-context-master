# Agent Operating Model

## Goal

Define clear decision boundaries between humans and agents so implementation
work can move quickly without ambiguity or accidental overreach.

## Human Responsibilities

Humans own:

- product scope and intent
- security exceptions and secret handling
- merge and release authority
- production access and production operations sign-off
- approval of breaking API, schema, or migration changes
- architectural exceptions to the documented standard

## Agent Responsibilities

Agents own:

- implementation within documented repository boundaries
- tests, regression coverage, and local verification
- documentation updates tied to behavior changes
- starter-kit and template maintenance
- surfacing risks, missing decisions, and unclear contracts

## Shared Expectations

- Keep code, tests, and docs aligned
- Prefer small, reviewable changes
- Make operational boundaries explicit
- Do not rely on undocumented local knowledge

## Agent Prohibitions

Agents must not:

- bypass documented quality gates
- weaken typing or test expectations without explicit instruction
- make security, release, or breaking-change decisions alone
- modify out-of-scope systems without explicit approval
