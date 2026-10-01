---
title: Task Syntax
weight: 40
description: Task line grammar, marker reference, dependencies
---

A task is a standard Markdown checkbox with emoji markers and inline fields layered on top. Everything mixes freely:

```markdown
## Launch
### Design
- [ ] Wireframes 🛫 2026-09-20 📅 2026-09-30 🆔 design 🔺
- [ ] Copy review 📅 2026-09-26 ⛔ design
- [x] Kickoff 🚩 2026-09-18
```

## Marker reference

| Syntax | Meaning |
|--------|---------|
| `- [ ]` | Open task |
| `- [x]` | Completed (changeable in settings) |
| `- [-]` | Cancelled (changeable in settings) |
| `🔺` | Critical |
| `⏫` | Highest priority |
| `🔼` | High priority |
| `🔽` | Low priority |
| `⏬` | Lowest priority |
| `📅 YYYY-MM-DD` | Due date |
| `🛫 YYYY-MM-DD` | Start date |
| `⏳ YYYY-MM-DD` | Scheduled date |
| `➕ YYYY-MM-DD` | Created date |
| `🆔 task-id` | Task ID |
| `⛔ task-id` | Depends on task |
| `✅ YYYY-MM-DD` | Completion date (added when *Track completion date* is on) |
| `🚩` / `#milestone` | Milestone (rendered as a diamond on the Gantt) |
| `[start:: …]` `[due:: …]` `[id:: …]` `[dependsOn:: …]` | Dataview-style inline fields, equivalent to the emoji markers |

`- [/]` is not a status of its own: a task counts as in progress once it has a start date in the past or a `#doing` / `#active` / `#next` tag.

## Dependencies

- `⛔ task-id` declares a dependency; while it is unfinished the card gets a red left border;
- the task editor's *Depends On* field is a dropdown listing all incomplete tasks that have an ID, sorted by due date (nearest first) — wiring dependencies never requires remembering IDs;
- in GTD classification, a task with a dependency or a `#waiting` tag goes to the Waiting column.

## What a drop writes

Dragging and the quick-move buttons write exactly the same things, fixed and spelled out (the settings page states them too):

**GTD containers**

- → In progress: adds `#doing` and a `🛫` start date of today;
- → Waiting: adds `#waiting`;
- → Done: writes the completion marker;
- → Inbox: clears the flow tags.

**Matrix containers**

- → Q1: high priority plus a due date of today;
- → Q2: high priority, due date cleared;
- → Q3: low priority plus a due date of today;
- → Q4: lowest priority, due date cleared.

(The importance side of each quadrant write is constrained: Q1/Q2 only offer high and above, Q3/Q4 only medium and below or nothing — no choice can push a task into the other half. Urgency has no marker of its own and is expressed through the due date.)

If the write would leave a start date after the due date, a dialog asks whether to move the due date to today or keep both and mark the task `#due-date-conflict`.
