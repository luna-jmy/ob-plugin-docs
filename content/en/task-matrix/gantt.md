---
title: Gantt Guide
weight: 30
description: Timeline, Mermaid preview and export, holiday scheduling
---

The Gantt chart is a **mode**, not a fifth panel: click *Gantt mode* in the toolbar from any panel mode and the main area becomes the timeline while the toolbar gains the Gantt's own controls (time scale and grouping). Leaving it restores the panel mode you were on.

{{< screenshot src="images/task-matrix/gantt-view.png" caption="Gantt mode: the task column and the timeline" >}}

## The timeline

- **Scales**: day / week / month / year. `Ctrl` + wheel zooms between them; drag the timeline to pan — no need to hunt for the scrollbar;
- **Today line**: a dashed red line. Entering Gantt mode scrolls to today automatically (it waits until it can measure its own width, so this works in the sidebar too), and *Jump to today* in the toolbar brings it back after panning or zooming away;
- **Task column**: the left column lists tasks and follows the timeline's vertical scroll. Its width is set by dragging the divider (or focusing it and using arrow keys, `Shift` for bigger steps); the width is saved, can be set in settings, and never squeezes the timeline out of view;
- **Every row carries a `✎` button**, so editing never requires knowing about right-click (right-clicking a bar still opens the same menu: edit / open note; a left click opens the note, same as clicking a card in the panel views).

## Bars and markers

- Bar colors are configurable per state (mapping to Mermaid's `active` for open, `done` for completed, `crit` for critical, plus a color for everything else) — type any CSS color or click a swatch;
- a task with only one date still gets a bar: the missing end is inferred and drawn with a dashed orange outline, and the sidebar shows "missing dates";
- `🚩` / `#milestone` renders as a diamond; `🔺` / `#crit` gets a red outline; weekends are shaded;
- tasks with no start and no due date cannot be placed on a timeline and are left out — the sidebar header reports how many, so nothing disappears silently.

## Grouping

Sections group by **folder, note, GTD state, or quadrant** — or turn grouping off for a single flat list. Grouping by note gives one section per note (named after the note, ordered by path), keeping a note's tasks together even when they span several folders' worth of projects. Section keys for folder, GTD state, and quadrant are shared with the panel views: collapsing a section in the Gantt collapses the matching container there too.

## Mermaid preview and export

The Gantt area has two tabs: the **timeline** and a **Mermaid preview**. The preview is generated from the current Gantt state (filters, grouping, collapsed sections), so it is never a second source of truth: there is no code box to edit, and collapsed sections are left out just like on screen.

The preview toolbar carries two toggles (today's line, weekend marking) and two date fields (extra holidays and make-up workdays), which recompute the preview as you type. The per-year holiday tables live in settings (below).

**Four exports**:

- **Export code**: copies the generated Mermaid to the clipboard;
- **Write to note**: picks a note and replaces what sits between the configured markers (`%% task-matrix:start %%` … `%% task-matrix:end %%`), touching nothing else; when the note has no markers yet, the block is appended at the end;
- **Export SVG**: vector output — stays sharp and remains editable elsewhere;
- **Export JPG**: a 2x bitmap with a background that follows your theme, handy for chat and documents. Both land in your Obsidian attachment folder with a timestamped name, and the path is copied to the clipboard.

## Holiday scheduling

Holiday tables are kept **per year** (Settings → Public holiday schedule): add a year, then fill in **Holidays** (`10-01~10-07`; `~` or `至`; ranges may cross into the next year) and **Make-up workdays** (working weekends). Whatever the Gantt spans is applied automatically — the shaded columns in the timeline and the exported `excludes` / `includes` lines always agree, and a working Saturday is never shaded. Ranges are expanded to individual dates when exporting, as Mermaid requires. The two date fields on the preview tab are only for one-off additions.

## Days on bars

Gantt bars can show a day count: off, calendar days (inclusive), or workdays. Workdays reuse the same calendar as the shaded columns and the export: calendar days − weekends (when weekend marking is on) − public holidays + make-up workdays. When a bar is too narrow the label moves to its right, and hovering a bar always reports both counts.
