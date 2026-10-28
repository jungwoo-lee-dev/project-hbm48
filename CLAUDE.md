# CLAUDE.md

Guidance for Claude working in this repo. Keep this file short. Detailed lore lives in `docs/canon/`.

## Project
HBM48: a short-form (9:16, ≤3 min, usually 1–2 min) idol drama series with dry workplace humor. The base mood is office-worker fatigue and disillusionment (社畜); comedy is seasoning, not the main dish. Eight Japanese fab workers in Saijo, Higashihiroshima form an idol group to escape underpay and overtime, and end up reviving their town.

## Sources of truth
- World and tone: `docs/canon/world.md`
- Members and pairs: `docs/canon/members.md`
- Decisions: `docs/decisions/` (read before changing direction; add a new record when you do)

If a script conflicts with canon, canon wins. If canon needs to change, propose it to the user first. Don't change it on your own.

## Hard rules
- All members are Japanese. The Photolithography member is the lead/center.
- Audio is Japanese; subtitles are JA/KO/EN. Plan in Korean, write dialogue directly in Japanese. See `docs/decisions/0004-languages.md`.
- Everything committed to GitHub is in English (docs, decisions, commits, PRs). The repo doesn't target Korean readers. Korean is for local planning files only.
- Original work only. Don't use Love Live!, Aqours or μ's names, characters, songs, logos or art. "Inspired by" is fine; copying isn't.
- Keep every company fictional. Don't name, or use the logos of, real semiconductor companies (Japanese or Korean) or real people.
- The competitor rivalry is friendly and comedic. Never mock nationalities or real people.
- Keep technical jokes accurate. Process terms should be used correctly.
- Never commit secrets, API keys or media. Media goes to the private Hugging Face dataset (see Data below).

## Workflow
1. Each episode lives in `episodes/epNNN-slug/` (copy `episodes/_template/`).
2. Order: `script.md` → canon check → `shotlist.md` → render in `video/`.
3. Work on a branch (`ep/NNN-slug` or `feat/...`), open a PR to `main`, and keep PRs small.
4. Commit messages: imperative, short (`Add ep003 script`, `Fix CVD member voice line`).

## Tooling
- Everything runs from the project `.venv/` (uv, Python 3.12). Use `uv run <cmd>` (e.g. `uv run gh ...`). Don't install tools globally. See `docs/decisions/0002-project-local-tooling.md`.

## Data
- The GitHub repo is public. Three tiers (`docs/decisions/0005-private-canon.md`): simple concept → GitHub (`docs/concept.md`); story details (`docs/canon/`, `episodes/epNNN-*/`) → local only, gitignored; big data → HF.
- All media (art, backgrounds, audio, footage, renders) lives in the private HF dataset `jungwoo-lee-dev/project-hbm48`. `assets/` is the local copy and is gitignored.
- Pull: `uv run hf download jungwoo-lee-dev/project-hbm48 --repo-type dataset --local-dir assets`
- Push: `uv run hf upload jungwoo-lee-dev/project-hbm48 assets . --repo-type dataset`
- Never make the dataset public or link it from public pages. See `docs/decisions/0003-media-on-hugging-face.md`.

## Video stack (planned)
- Remotion (React + TypeScript) in `video/`, one composition per episode, 1080×1920 @ 30fps.
- Not scaffolded yet. Set it up when the first episode is ready to render, and record the choice in `docs/decisions/`.

## Subagents
- `scriptwriter`: drafts and revises episode scripts
- `canon-keeper`: read-only reviewer for continuity and hard rules
- `video-engineer`: builds and fixes Remotion compositions
