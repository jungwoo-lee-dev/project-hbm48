# 0005: Three tiers for story data

Date: 2026-10-28
Status: Amended by 0007 (story details moved from local-only to a private repo)

## Context
The GitHub repo `project-hbm48` is public. Story details shouldn't be public before release, but a simple concept can be.

## Decision
| Tier | What | Where |
|---|---|---|
| Public | Simple concept (`docs/concept.md`), decisions, templates, code | GitHub |
| Local | Story details: canon (`docs/canon/`), episode folders (`episodes/epNNN-*/`) | Local only, gitignored |
| Big / important data | Media, renders, other large files | Private HF dataset (see 0003) |

- Canon and episode files keep their local paths, so `CLAUDE.md`, subagents and skills keep working unchanged.
- `episodes/_template/` and `docs/canon/README.md` stay tracked.
- Anything added to `docs/concept.md` must stay high-level: no company names, rival details, plot beats or character details.

## Consequences
- Local details have no git history or backup. Keep your own backup.
- Early English drafts from the initial scaffold are still in public git history. They're high-level placeholders, so history isn't rewritten.
