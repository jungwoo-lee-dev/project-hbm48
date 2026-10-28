# 0006: Episode runtime

Date: 2026-10-28
Status: Accepted

## Context
The original plan capped episodes at 60 seconds. Platforms no longer require that: YouTube Shorts allows up to 3 minutes (since October 2024), TikTok allows 10 minutes or more, and Instagram Reels over 3 minutes aren't recommended to new viewers. Short-form drama episodes usually run 1–3 minutes. The series' tone also needs silence and pauses, which 60 seconds squeezes out.

## Decision
- Hard cap: 3 minutes per episode, so every episode qualifies as short-form on all three platforms.
- Target: 1–2 minutes. Go longer only when an emotional beat needs it.
- Keep a hook in the first 2–3 seconds.

## Consequences
- Updated `CLAUDE.md`, `README.md`, `docs/concept.md`, the episode templates, the PR template, the `scriptwriter` and `canon-keeper` agents, and the `canon-check` skill. The script template now has JA line, KO gloss and nuance/TL columns (per 0004).
- Platform limits change; recheck them before release.
