# 0007: Story details in a private repo

Date: 2026-10-28
Status: Accepted (amends 0005)

## Context
0005 kept story details local-only and gitignored, because this repo is public. A friend is joining as a co-creator (story and music, with a GPU workstation). Local-only files can't be shared, have no history and no backup.

## Decision
| Tier | What | Where |
|---|---|---|
| Public | Simple concept (`docs/concept.md`), decisions, templates, code | This repo |
| Private | Story details: canon, episode notes, scripts, shot lists | `jungwoo-lee-dev/project-hbm48-story`, cloned to `story/` |
| Big / important data | Media, renders, other large files | Private HF dataset (see 0003) |

- `story/` is gitignored here. It's a separate git repo with its own commits and pushes.
- Main work still happens in this folder. Paths: `story/canon/`, `story/episodes/epNNN-slug/`.
- `episodes/_template/` stays in this repo. New episodes are copied from it into `story/episodes/`.
- The private repo may be written in Korean. This repo stays in English (0004).
- Collaborators get access by being invited to the private repo.

## Consequences
- Fresh setup needs two clones: this repo, then the story repo into `story/`.
- Changes to story and code are committed separately.
- For media access, a collaborator needs access to the private HF dataset as well. A dataset under a personal account can't add collaborators, so this may need a Hugging Face organization.
