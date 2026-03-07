# Bootstrap Workflow

## Goal

Create new repositories that begin aligned with the standard by default instead
of relying on manual copy-paste and post-hoc cleanup.

## Default Bootstrap Model

Use a template-plus-initializer approach:

- starter kit provides the file and directory skeleton
- bootstrap tool fills repository-specific metadata and paths

Do not clone the standards repository as the base of a product repository.

## Recommended New Repository Flow

1. Create an empty target repository or working directory.
2. Run `repo-init` with the Python profile and repository metadata.
3. Review generated `AGENTS.md`, `README.md`, and package naming.
4. Run the generated repository quality gates.
5. Make the initial commit on `main`.

## `repo-init` Inputs

Required:

- `--profile`
- `--repo-name`
- `--package-name`
- `--description`

Optional:

- `--repo-type`
- `--python-version`
- `--author`
- `--output-dir`
- `--no-install`

## Expected Output

The generated repository should contain:

- a concrete `AGENTS.md`
- baseline Python tooling files
- a standard `src/` and `tests/` layout
- a README with the repository purpose and workflow entry points
