---
title: Guide
weight: 20
description: Layout, the four panel views, task cards, and filtering
---

## Layout

The view is three rows, top to bottom:

1. **Toolbar** — new task, refresh, the four panel modes (List / GTD / Matrix / Calendar), a **Gantt mode** toggle, and **Hide filters** (the filter bar is expanded by default). One expand/collapse button announces what it will do next (it reads *Collapse all* only when every container is open). Clicking **Gantt mode** swaps the panel buttons for the Gantt's own controls (time scale and grouping); the button then reads *Exit Gantt mode*, and the panel mode you were on is remembered;
2. **Filter bar** — search, status chips, start and due date ranges, sorting, a live `shown/total` count, and a clear button;
3. **Main area** — equally sized containers holding task cards, so the grid stays symmetrical at any window width.

{{< screenshot src="images/task-matrix/filter-bar.png" caption="The toolbar and filter bar" >}}

## The four panel views

| View | Layout | Best for |
|------|--------|----------|
| **📋 Note list** | A container per note; with grouping on, containers sit under collapsible folder sections | Browsing everything |
| **📥 GTD** | Four containers: Inbox, In progress, Waiting, Done | Working through a flow |
| **🔳 Matrix** | Four containers: Q1–Q4 | Deciding what matters |
| **🗓 Calendar** | Month, week, or list | Planning by date |

Hovering a calendar entry gives an instant tooltip with the task and its note — it does not wait for the page-preview delay. The Gantt chart is a *mode* rather than a fifth panel; see the [Gantt guide](gantt/).

## Task cards

Each card shows the rendered description, a status badge, and chips for priority, dates, task ID, and dependencies:

- ✓ Complete / ↺ Reopen (optionally adds `✅ YYYY-MM-DD`);
- ▶ Start (adds `🛫` and `#doing`);
- ✕ Cancel;
- ✎ Edit — description (a two-line field, tags written straight into it, with clickable tag chips underneath), priority, dates, ID, dependency;
- 🗑 Delete;
- 1–4 and 收/进/等 quick moves in the matrix and GTD views;
- click the card to open the note it lives in.

A task whose `⛔` dependency is unfinished gets a red left border.

**Tags are written in the description**, exactly where they sit in the note — no separate tags field, so there is only one place to look. Underneath sits a row of tag chips: click one to write it into the description, click again to take it out. The chips come from the tags actually used in your vault (most used first, plus this task's own). On save the tag set is rewritten at the end of the line, and only when it actually changed; the rest of the line stays as it was. If nothing changed, the line is not rewritten at all.

**The note list uses the same task cards** as GTD and matrix — complete, start, cancel, edit, and delete all work — with two differences: the note path is not repeated on every card (the container *is* the note; with folder grouping the card shows just the note name), and cards cannot be dragged between containers (a list container is a place, not a status).

## How tasks are classified

- **GTD** comes from tags (`#waiting`, `#doing`, `#blocked`), start dates, and dependencies; an overdue task that never started falls back to Inbox rather than sitting in a column of its own;
- **Matrix** treats high priority and above as important, and anything due inside the configured urgent window (1–7 days) as urgent;
- **Scheduling** is only ever written as plain markdown: `📅` due, `🛫` start, `⏳` scheduled, `✅` done, `➕` created, `🆔` task ID, `⛔` dependency, plus your own `#tags`. See the [task syntax](syntax/) for the full grammar.

## Filtering

- **Search** matches description, file path, task ID, and dependency ID;
- **Status chips**: open, to be started, overdue, completed, cancelled — with *Active only* / *Hide cancelled* / *All statuses* presets;
- **Marker chips**: filter by what is actually inside the brackets (`[ ]`, `[x]`, `[-]`, `/`, or any custom marker); candidates come from your vault, so unused markers never appear;
- **Start and due dates**: a preset (today, this week, this month, this year, custom) plus an explicit range; editing either end switches to custom automatically;
- **Sort**: due ↑, due ↓, start ↑, priority, file name;
- the count shows how many indexed tasks survive the filters, and **Clear filters** returns to the neutral baseline.

## Drag and drop

- drop a card on a **GTD container** to change its state, or on a **matrix container** to change its quadrant;
- the drop writes exactly what the quick-move buttons write (see the [syntax page](syntax/#what-a-drop-writes));
- drag and drop is desktop only; on mobile use the quick-move buttons.

## Mobile

The toolbar and filter bar wrap instead of overflowing; containers fall back to a single column on narrow screens; every card action stays reachable by tap.
