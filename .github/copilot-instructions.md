<!-- file: .github/copilot-instructions.md -->
<!-- version: 1.2.0 -->
<!-- guid: c3d4e5f6-a7b8-9012-cdef-123456789012 -->
<!-- last-edited: 2026-06-13 -->

# gha-detect-languages — Additional Context

Org-wide coding standards (file headers, language rules, commit format) are at
**<https://github.com/falkcorp/.github>** and apply automatically to this repo.

For full project context: **CLAUDE.md** at the repo root.

## Project overview

GHA composite action: detect repository languages. Language: Python/YAML.
All logic is embedded directly in `action.yml` as a `shell: python` run step —
there is no separate `src/` directory needed for the detection script.

## Key files

- `action.yml` — Main composite action with embedded Python script (all logic lives here)
- `README.md` — Usage documentation and examples
- `CHANGELOG.md` — Version history

## Critical constraints

- All language detection logic changes go in the embedded Python script inside `action.yml`.
- Single-file composite action pattern — do not split into a separate Python package.
