---
title: Settings
weight: 50
description: Every setting, grouped the way the view is
---

Open via: Obsidian settings → Community plugins → **Task Matrix**. Settings mirror the view's structure.

## Interface

| Setting | Description |
| --- | --- |
| Interface language | Automatic (follow Obsidian) / Chinese / English |

## Scanning

| Setting | Default | Description |
| --- | --- | --- |
| Scan folders | `500 Journal, 100 Projects` | Comma-separated (full-width commas and semicolons work too), multi-level paths like `300 Resources/360 WorkMemos`, matched case-insensitively; **clear to scan the whole vault** (slow on large vaults) |
| Excluded folders | — | Tasks here stay out of every view and count |

## Task markers

- **Completion markers / Cancelled markers**: what the brackets must contain (defaults `x` / `-`);
- **Ignored markers**: bracket contents that are not tasks at all;
- **Track completion date**: adds `✅ YYYY-MM-DD` on completion.

## Display

- Default view and open location;
- **Urgent window**: how many days ahead counts as urgent (1–7);
- Due-date range, completed-task range, **hide tasks that start far ahead**: how much gets laid out at once;
- Show completed tasks without a due date.

## New tasks

| Setting | Default | Description |
| --- | --- | --- |
| Target note path | Today's journal | Where new tasks go; supports `{{title}}`, `{{date}}`, `{{time}}`, and `{{date:FORMAT}}` placeholders; the note is created when missing; **empty means the note you have open** |
| Target heading | empty | Insert under this heading; empty appends at the end |
| Journal template | — | The note copied when the target note doesn't exist yet (`{{title}}` is its file name; `<% … %>` commands are left to Templater) |

## Note list

- **Group by folder** (off by default): off — one container per note (the `+` in the container header adds a task to that note); on — containers sit under collapsible folder sections;
- section names use the **full path of your scan folders**: a sub-folder added to the scan list becomes its own section, and everything below it stays there; without scan folders, each note's own folder path is used.

## GTD and matrix

Split into two halves — what decides the column, and what a drop writes. Only the tag vocabulary and the urgent window are adjustable; the rules themselves are stated on the settings page rather than offered as switches, because a switch that breaks classification or dragging is not a parameter.

**Classification**

- **Waiting tags** and **In-progress tags**: the tags that decide the column (and the first entry is what a drop writes — one list for both, so a dropped task cannot bounce back);
- **Urgent days**: how far ahead counts as urgent, deciding the urgent side of the matrix;
- the rule order is listed right there: a dependency or waiting tag → Waiting; an in-progress tag → In progress; due date passed → Overdue; start date passed → In progress; start date ahead → To be started (folded into Inbox); otherwise Inbox.

**Dragging**

- **Enable dragging**: the master switch. Off — containers stop accepting drops and cards cannot be dragged; the quick-move buttons and the Gantt context menu keep working. Everything below is disabled while it is off;
- **what a drop writes** is fixed and spelled out (see the [syntax page](syntax/#what-a-drop-writes));
- **what each quadrant writes**: one dropdown per quadrant for importance, limited to that quadrant's own side — high and above for Q1/Q2, medium and below (or nothing) for Q3/Q4.

## Calendar view

First day of week, weekends in the month and week views, whole month in the list view, and spreading in-progress tasks across their date range.

## Gantt view

- **Days on bars**: off / calendar days (inclusive) / workdays (sharing the same calendar as the shaded columns and the export);
- **Bar colors**: one per Mermaid state (`active` / `done` / `crit` / everything else), typed as any CSS color or picked from swatches;
- **Task column width**: also draggable right in the Gantt;
- **Diagram title and markers**: the `title` line of the exported code, and the marker pair **Write to note** replaces between (default `%% task-matrix:start %%` … `%% task-matrix:end %%`). The today line, weekend marking, and the two date lists live on the preview tab so you can adjust them while looking at the diagram.

## Public holiday schedule

Kept per year, because that is how holidays are announced: add a year, then fill in **Holidays** (`10-01~10-07`; `~` or `至`; ranges may cross years) and **Make-up workdays** (working weekends). Ranges are expanded to individual dates on export (a Mermaid requirement). Whatever the Gantt spans is applied automatically; the preview-tab date fields are for one-off additions only.
