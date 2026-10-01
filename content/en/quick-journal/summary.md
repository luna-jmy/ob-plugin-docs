---
title: Journal Summary
weight: 30
description: The component-based summary view and query blocks
---

The command *Open journal summary* opens the dashboard: data from every period gathered into one arrangeable board. The toolbar gear enters **edit mode** — drag to reorder, delete, add components; the summary layout's query list is also maintained in edit mode.

{{< screenshot src="images/quick-journal/summary-view.png" caption="The journal summary view" >}}

## Components

| Component | What it shows |
| --- | --- |
| **Capture bar** | A quick-capture strip at the top covering day / week / month / year sections |
| **Task chart** | Task completion metrics + bars; weekly / monthly periods aggregate by day, quarterly / yearly by month |
| **Check-in summary** | A ratio bar per check-in field: done / not done / unrecorded |
| **Data trend** | A line chart of one selected data field (with axes and latest / max / min) |
| **Calendar** | Year / month chips plus a week-number column; clicking a date or week number opens the matching journal / review note; days with done tasks carry a badge, days with records a dot |
| **Heatmaps** | One for task completion, one for record activity; the shape adapts to the period: week = 7 big cells, month = calendar cells, year = small cells |
| **Recent notes** | The latest 8 entries of the content stream |
| **Query blocks** | Render the `dataview` / `dataviewjs` queries you add manually (below) |

All charts are drawn natively with no external dependencies; toggles like *show completed tasks* and *include non-daily tasks* live in settings.

## Query blocks

The query-block component renders queries you **add manually in edit mode** — no presets, and it does not auto-detect code blocks already in your journals. Each query (title + kind + code) lives in the plugin configuration, editable at any time:

- exactly two kinds: `dataview` and `dataviewjs`, rendered by the Dataview plugin (a hint appears when it's absent);
- every query can carry a **title**, shown above the result;
- typical use: a table of recent journals or a cross-folder task list pinned on the summary.

````markdown
```dataview
TABLE done, weight FROM "500 Journal/540 Daily" LIMIT 7
```
````

## Panel vs. summary

- The **quick panel** is for "capture it now": input on top, the stream right below;
- the **summary** is for "look back": charts, calendar, trends, and query blocks.

Both read the same journal data, and each remembers where you opened it (tab or right sidebar).
