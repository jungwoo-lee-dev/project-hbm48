# 0005: Keep canon out of the public repo

Date: 2026-10-28
Status: Accepted

## Context
The GitHub repo `project-hbm48` is public. The canon files in `docs/canon/` hold the core story and world details, which shouldn't be public before release.

## Decision
- `docs/canon/*` is gitignored. Only `docs/canon/README.md` is tracked.
- The canon files stay at the same local paths, so `CLAUDE.md`, subagents and skills keep working unchanged.

## Consequences
- Canon has no version history and no backup in git. A private backup location still needs to be decided (for example the private HF dataset).
- Early English drafts from the initial scaffold are still in public git history. They're high-level placeholders, so history isn't rewritten.
