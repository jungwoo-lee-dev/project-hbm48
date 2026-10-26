# 0002: Keep project tooling in `.venv`

Date: 2026-10-26
Status: Accepted

## Context
The machine has no system Python, and global installers can need admin rights (the `gh` MSI failed with exit code 1603). We want the project to be self-contained.

## Decision
- All project tooling runs from the project `.venv/`, managed by [uv](https://docs.astral.sh/uv/).
- Python 3.12 is pinned in `.python-version`. Add Python packages with `uv pip install` (or `uv add` once there's a `pyproject.toml`).
- Non-Python CLIs go in `.venv/Scripts/` as portable binaries. Currently: GitHub CLI `gh` v2.103.2.
- Run tools with `uv run <cmd>` or after activating the venv (`.venv\Scripts\activate`).
- Node/Remotion is the exception: it uses `video/node_modules/` when it's set up.

## Consequences
- `.venv/` is gitignored, so recreating it deletes the portable binaries. To restore `gh`, download `gh_<version>_windows_amd64.zip` from https://github.com/cli/cli/releases, verify it against `gh_<version>_checksums.txt`, and copy `bin/gh.exe` into `.venv/Scripts/`.
- Nothing is installed system-wide except `uv` itself.
