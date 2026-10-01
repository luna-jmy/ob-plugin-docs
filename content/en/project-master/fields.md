---
title: Field Reference
weight: 30
description: Detection rules, field mapping, status and priority
---

## Detection rules

The plugin scans only the **scan folders** in settings (default `100 Projects`, multiple allowed; `excludedFolders` defaults to `templates`). A note inside them is recognized as a project when either:

- its frontmatter has `type: project`, or
- its `tags` include `project`.

Minimal working example:

```yaml
---
type: project
status: active          # Chinese and English both work: 执行中 / active
start_date: 2026-01-01
due_date: 2026-03-31
---
```

## Fields

The table lists the **default field names**; every one of them can be renamed in *Settings → Field mapping* (that's the only place to touch when you switch templates).

| Field | Type | Description |
| --- | --- | --- |
| `status` | enum | Project status, see the table below; Chinese and English values both recognized |
| `start_date` | date | Start date (YYYY-MM-DD) |
| `due_date` | date | Due date |
| `end_date` | date | Fallback due date: read when `due_date` is missing |
| `completion_date` | date | Actual completion date |
| `progress` | number | Progress percentage 0–100 |
| `priority` | number | Priority **1–5, 1 highest**: 1🔴 highest, 2🟠 high, 3🟡 medium, 4🔵 low, 5⚪ lowest |
| `area` | text | The project's area, a **single value** (used for grouping and filtering); arrays in legacy notes read their first entry |
| `objective` | text | Project objective |
| `context` | text | Background / context |
| `remark` | multiline | Free-form notes: status changes, decisions, blockers |
| `project-leader` | text | Project leader |
| `project-members` | list | Members |
| `long-term` | boolean | Long-term project: **stays off the Gantt chart and is exempt from every date filter**; appears only in the left panel (pinned to the top) |
| `main-project` | boolean | Main-project flag: when a folder holds several project notes, the flagged one represents the group; more than one note with no flag raises a "multiple projects" hint |
| `project-id` | text | Project ID |
| `color` | color | Custom Gantt bar color (a CSS color); invalid values are ignored with a notice |

## Status values

Seven statuses with equivalent Chinese aliases (extensible in settings); the default order is the order of the create-dialog dropdown:

| Value | Chinese alias | Meaning |
| --- | --- | --- |
| `inbox` | 未开始/待启动 | Not started |
| `draft` | 起草/构思中 | Drafting / ideating |
| `active` | 执行中 | In progress |
| `on-hold` | 暂停 | On hold |
| `completed` | 完成 | Completed |
| `cancelled` | 取消 | Cancelled (**still drawn on the Gantt chart**; hide it with the status filter) |
| `archived` | 归档 | Archived |

## Date fallbacks

When dates are incomplete, the *Settings → Global* fallback applies — by default **offset by days** (7):

- `due_date` present, `start_date` missing → start = due − 7 days;
- `start_date` present, `due_date` (and `end_date`) missing → due = start + 7 days;
- neither present → the project stays off the chart, and the reason and count are shown at the top of the view.

## Gantt bar colors

Four configurable classes: **active** blue, **completed** green, **critical** (priorities 1 / 2, drawn with an outline) red, **other statuses** muted. A note's `color` field overrides the class for a single project.

## The quick-project marker

A path segment named `快速项目` (configurable) has a special grouping meaning: group partitioning stops at that segment and titles join with " > ". Projects created through the *new project* dialog land under the `快速项目/` folder by default and form their own group.
