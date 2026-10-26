---
name: canon-check
description: Review a script, shot list or canon change for continuity, technical accuracy and hard-rule violations. Use before merging story content.
---
Run the `canon-keeper` subagent on the given path (default: files changed vs `main`, from `git diff --name-only main`). Relay its findings grouped by severity. Don't edit anything unless the user asks.
