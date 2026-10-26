# CLAUDE.md

Guidance for Claude working in this repo. Keep this file short. Detailed lore lives in `docs/canon/`.

## Project
HBM48: a short-form (9:16, ≤60s) idol comedy/drama series. Eight Japanese fab workers in Saijo, Higashihiroshima form an idol group to escape underpay and overtime, and end up reviving their town.

## Sources of truth
- World and tone: `docs/canon/world.md`
- Members and pairs: `docs/canon/members.md`
- Decisions: `docs/decisions/` (read before changing direction; add a new record when you do)

If a script conflicts with canon, canon wins. If canon needs to change, propose it to the user first. Don't change it on your own.

## Hard rules
- All members are Japanese. The Photolithography member is the lead/center.
- Original work only. Don't use Love Live!, Aqours or μ's names, characters, songs, logos or art. "Inspired by" is fine; copying isn't.
- Keep every company fictional. Don't name, or use the logos of, real semiconductor companies (Japanese or Korean) or real people.
- The competitor rivalry is friendly and comedic. Never mock nationalities or real people.
- Keep technical jokes accurate. Process terms should be used correctly.
- Never commit secrets, API keys or large raw media (see `.gitignore`).

## Workflow
1. Each episode lives in `episodes/epNNN-slug/` (copy `episodes/_template/`).
2. Order: `script.md` → canon check → `shotlist.md` → render in `video/`.
3. Work on a branch (`ep/NNN-slug` or `feat/...`), open a PR to `main`, and keep PRs small.
4. Commit messages: imperative, short (`Add ep003 script`, `Fix CVD member voice line`).

## Video stack (planned)
- Remotion (React + TypeScript) in `video/`, one composition per episode, 1080×1920 @ 30fps.
- Not scaffolded yet. Set it up when the first episode is ready to render, and record the choice in `docs/decisions/`.

## Subagents
- `scriptwriter`: drafts and revises episode scripts
- `canon-keeper`: read-only reviewer for continuity and hard rules
- `video-engineer`: builds and fixes Remotion compositions
