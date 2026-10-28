---
name: canon-check
description: Review a script, shot list or canon change for continuity, technical accuracy and hard-rule violations. Use before merging story content.
---
Run the `canon-keeper` subagent on the given path. Story files (`docs/canon/`, `episodes/epNNN-*/`) are gitignored, so `git diff` won't list them: default to the episode folder or canon file being worked on, and ask if unclear. Relay its findings grouped by severity. Don't edit anything unless the user asks.
