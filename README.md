# HBM48

A short-form vertical video series (9:16, under 60s) about **HBM48**, an idol group made up of eight overworked fab workers in Saijo, Higashihiroshima.

Original and fictional. It's inspired by school-idol anime but uses none of their assets, names or trademarks.

## Concept
- Eight members, each from a different semiconductor process area.
- **48** means four pairs of two ("twins"), each pair from areas that naturally work together.
- They're underpaid and overworked. To beat the bonuses competitors pay, they start an idol group, and their success brings their quiet rural town back to life.

## Repo layout
| Path | What |
|---|---|
| `CLAUDE.md` | Main instructions for Claude (the primary developer) |
| `.claude/` | Claude Code settings, subagents, skills |
| `docs/canon/` | Story world and characters (source of truth) |
| `docs/decisions/` | Short records of key decisions |
| `episodes/` | One folder per short: script, shot list, notes |
| `video/` | Video rendering code (Remotion, not yet scaffolded) |
| `assets/` | Images, backgrounds, audio (large files are not committed) |

## Working with Claude
Open the repo in Claude Code. Useful entry points:
- `/new-episode <idea>`: drafts a new episode folder from the template
- `/canon-check <path>`: checks a script against the canon docs
