---
title: FAQ & Limitations
weight: 60
description: Data, privacy, and known limits
---

## FAQ

**Where do tasks live?**

In your notes, as Markdown checkboxes — no database, no export step. Every dashboard action (checking, rescheduling, dragging between columns) ultimately writes back to that one task line; uninstall the plugin and every task is still there.

**Why are some tasks missing from the Gantt?**

Tasks with no start and no due date cannot be placed on a timeline and are left out; the sidebar header reports how many, so nothing disappears silently. A task with a single date still gets a bar — the missing end is inferred and drawn with a dashed orange outline.

**What status is `- [/]`?**

None of its own. A task counts as in progress once it has a start date in the past or a `#doing` / `#active` / `#next` tag — the `/` marker itself plays no part.

**Can I scan the whole vault?**

Yes (clear the scan-folders setting), but it is noticeably slow on large vaults — prefer specific folders plus exclusions.

**The plugin doesn't show up after a manual install?**

The folder name must match the plugin id: `task-matrix-dashboard`. Obsidian loads nothing else.

## Data & privacy

Task Matrix runs entirely inside your vault:

- no network requests, no telemetry, no account or sign-in;
- it only reads and writes markdown files that already exist in your vault, and only the task line you act on;
- settings are stored through Obsidian's plugin data API inside your vault's `.obsidian` folder.

## Known limitations

- drag-to-restate is desktop only (use the quick-move buttons on mobile);
- Mermaid does not support per-task colors (a Mermaid limitation);
- the new-task dependency dropdown lists only *incomplete* tasks that have an ID.
