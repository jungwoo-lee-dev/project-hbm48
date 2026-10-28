---
name: new-episode
description: Create a new HBM48 episode folder from the template and draft its script. Use when the user wants a new short or gives an episode idea.
---
1. Find the next number in `story/episodes/` (ep001, ep002, …). Make a short kebab-case slug from the idea.
2. Copy `episodes/_template/` to `story/episodes/epNNN-slug/`.
3. Fill `notes.md` with the idea, featured members and pair.
4. Have the `scriptwriter` subagent draft `script.md`.
5. Have the `canon-keeper` subagent review it, then fix any `block` issues.
6. Summarize for the user: logline, featured members, open questions.
