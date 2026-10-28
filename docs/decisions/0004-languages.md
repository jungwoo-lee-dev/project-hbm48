# 0004: Languages

Date: 2026-10-28
Status: Accepted

## Context
HBM48 is a Japanese-language anime short set in Hiroshima. The creator's native language is Korean, and the audience spans Japan, Korea and English-speaking viewers. Japanese idol culture, office-worker speech, Hiroshima dialect and puns don't survive translation from a finished Korean script.

## Decision
- **Audio:** Japanese. Locals use Hiroshima dialect (広島弁) where it fits the character.
- **Subtitles:** Japanese, Korean and English.
- **Planning:** Concepts, canon and episode beats are written in Korean, with Japanese terms in parentheses where needed. English drafts get converted when they're next revised.
- **Dialogue:** Written directly in Japanese, not translated from Korean. Each line gets a Korean gloss and nuance notes so the creator can review it.
- **Subtitle source:** Korean and English subtitles are translated from the Japanese dialogue, so all three match the audio. Jokes that can't survive translation get marked in the script with a note like `[TL: ...]`.
- **Review:** A native Japanese speaker checks dialogue before release, especially dialect and idol slang.

## Consequences
- Scripts carry three layers: Japanese line, Korean gloss, translator notes.
- Wordplay is designed in Japanese first.
- A shared glossary (`docs/canon/glossary.md`) will keep fab and idol terms consistent across the three languages. It gets added when it's first needed.
