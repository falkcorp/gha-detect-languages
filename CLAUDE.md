<!-- file: CLAUDE.md -->
<!-- version: 1.0.0 -->
<!-- guid: a1b2c3d4-e5f6-7890-abcd-ef1234567890 -->
<!-- last-edited: 2026-06-13 -->

# gha-detect-languages

A composite GitHub Action that detects programming languages in a repository.

## Coding Standards

Org-wide coding standards are in the `.standards/` git submodule (cloned from
`https://github.com/falkcorp/.github`). Always clone with
`git clone --recurse-submodules` so these are available.

Key files:

- **File headers (MANDATORY):** `.standards/instructions/file-headers.md`
- **Commit format:** `.standards/instructions/commit-messages.md`

## Architecture

This is a single-file composite action. All detection logic is embedded as a
Python script directly inside `action.yml` using `shell: python`. There is no
separate source package.

**Key files:**

- `action.yml` — The entire action: inputs, outputs, and embedded Python
  detection script
- `README.md` — Usage documentation and examples
- `CHANGELOG.md` — Version history

## Design Pattern

- Composite action using `shell: python` to embed the entire Python script
- All environment variables passed as action inputs
- Outputs exposed via GitHub Actions output commands
- No external Python dependencies — stdlib only

## Build & Test

No build step required. To test locally, use `act` or push to a test branch and
observe the action output in GitHub Actions.

## Critical Constraints

- All language detection logic changes must be made in the embedded Python
  script within `action.yml`
- Do not split the action into a separate Python package
- Follow GitHub Actions composite action best practices
