# 0008: Limited animation

Date: 2026-10-28
Status: Accepted

## Context
Episodes are 1–2 minute vertical shorts built around silence, small expression changes and accurate on-screen fab details (monitors, SPC charts, whiteboards). The cast is eight characters over many episodes, so character consistency matters more than full motion. The creator's laptop (6 GB VRAM) can't run local video models; a collaborator's workstation (RTX 4090) can run local image models and LoRA training.

## Decision
- Use limited animation: character and background art, with camera moves (pan, zoom, push-in), expression swaps, blinks and mouth shapes, composed in Remotion.
- Build on-screen UI (phones, MES, SPC charts, whiteboards, title cards) in Remotion code, so numbers and Japanese text stay exact.
- AI image-to-video is allowed for one or two key shots per episode at most.
- The art tool (paid service, local model with character LoRA, or a human illustrator) is chosen after a pilot test, and gets its own decision record.

## Consequences
- Shot lists list art assets (`bg/…`, `characters/…`) and code-built UI (`ui:…`) separately.
- Performance scenes (dance) are decided later: limited staging or 3D.
- Check commercial-use terms for any AI tool before final use.
