---
title: Settings
weight: 40
description: The seven settings tabs and their defaults
---

Open via: Obsidian settings → Community plugins → **Project Master**. Seven tabs.

## Global

| Setting | Default | Description |
| --- | --- | --- |
| Scan folders | `100 Projects` | Where to look for project notes; multiple allowed |
| Excluded folders | `templates` | Folders left out of scanning |
| Quick-project marker | `快速项目` | The path segment with special grouping rules — see the [field reference](fields/#the-quick-project-marker) |
| Chinese status aliases | On | Chinese values like 执行中 in the status field are read as their English equivalents |
| Date fallback | Offset by days (7) | How incomplete dates are derived; alternatively "leave off the chart with a notice" |
| New-project template | empty | A template note applied when creating projects; empty disables it |
| Materials folder name | `资料` | Name of the companion materials subfolder |

## Field mapping

A table pairing each piece of information with the frontmatter field name it lives in; defaults are the names in the [field reference](fields/#fields). Switching templates means editing this one table — the code-side names never surface.

## Enums & display

- **Statuses**: order, Chinese aliases, and emoji for the seven default statuses;
- **Priorities**: emoji for levels 1–5 (default 1🔴 … 5⚪);
- **Gantt bar colors**: four classes — active (blue) / completed (green) / critical (red, priorities 1–2) / other statuses (muted).

## View preferences

| Setting | Default | Description |
| --- | --- | --- |
| Default grouping | Folder | Grouping used when the board opens |
| Default sort | Due date ascending | List ordering |
| Default zoom | Month | Gantt time level |
| Default year filter | Current year | The year preset on open |
| Notes per group | 5 | Cap on related notes listed under each group |
| Bar duration label | Off | Whether to show day counts on Gantt bars |
| Card font scale | 100% | Panel card text scaling |
| Sidebar width | unset | Remembered automatically once you drag the divider |

## Mermaid export

Title (default "项目进度甘特图"), today marker (on), exclude weekends (off), exclude / include dates, the fallback section name (default "默认项目"), and the write markers (`%% gantt-builder:start/end %%`).

## Holiday schedules

Per-year holiday date tables used to exclude holidays from Mermaid scheduling. Stored per year — add each year as needed.

## Language

Follow Obsidian / Chinese / English.
