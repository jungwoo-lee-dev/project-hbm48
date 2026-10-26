# 0003: Keep media in a private Hugging Face dataset

Date: 2026-10-26
Status: Accepted

## Context
The GitHub repo is public, and media files (character art, backgrounds, audio, footage, renders) are large and not meant to be public. Git handles large binaries poorly.

## Decision
- All media lives in the **private** Hugging Face dataset `jungwoo-lee-dev/project-hbm48`.
- `assets/` is the local working copy. It's gitignored except for `.gitkeep` files that keep the folder layout: `characters/`, `bg/`, `audio/`, `footage/`, `renders/`.
- Scripts, canon, shot lists and code stay on GitHub.
- Tooling: `huggingface_hub` (the `hf` CLI) in the project `.venv`, per 0002.

```powershell
uv run hf auth login        # once, with a write token
uv run hf download jungwoo-lee-dev/project-hbm48 --repo-type dataset --local-dir assets   # pull
uv run hf upload   jungwoo-lee-dev/project-hbm48 assets . --repo-type dataset             # push
```

## Consequences
- A fresh clone has no media until you log in and pull.
- The dataset must stay private and must not be linked from public pages (profile, website, README).
- Rendered Remotion output (`video/out/`) also goes to the dataset under `renders/`, never to git.
