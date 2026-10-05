---
title: Project Master
weight: 20
icon: fa-chart-gantt
description: An interactive Gantt chart generated straight from your project notes
---

Project Master turns your project notes into an interactive project board: a grouping panel on the left, Gantt and Mermaid views on the right — drag to reschedule, filter across dimensions, and keep long-term projects and milestones in view.

All data comes from your notes' **frontmatter** — no database, no changes to your existing note structure. The Gantt chart and the whole UI are drawn by the plugin itself: **zero plugin dependencies**.

{{< screenshot src="images/project-master/main-view.png" caption="The board: grouping panel on the left, Gantt on the right" >}}

## Highlights

- **Automatic project detection**: notes in the scan folders with `type: project` or a `project` tag land on the chart automatically — and every field name can be remapped to your own convention in settings;
- **Interactive Gantt**: drag bars to reschedule (written straight back to frontmatter), multiple zoom levels, a today line, and status / priority coloring;
- **Grouping panel**: group by folder / status / area and more; cards support drag-to-reorder and a full-page *panel mode*;
- **Multi-dimensional filters**: status presets (hiding completed / cancelled / archived by default), area, year, priority — the whole bar collapses when you need the space;
- **Create / edit projects**: a form-based creator (optionally starting from a template, with a companion `materials` folder), and click-a-card editing;
- **Mermaid export**: write the chart into a note as a Mermaid `gantt` block, or export SVG / JPG images; holiday-aware scheduling and weekend exclusion included;
- **Bilingual UI** following your Obsidian language by default.

## Install

{{% notice style="info" title="Requirements" %}}
Obsidian **1.8.7** or newer, **desktop only** (not available on mobile — the Gantt interactions are designed for mouse and keyboard).
{{% /notice %}}

1. Download the latest release from [GitHub Releases](https://github.com/luna-jmy/ob-project-center/releases);
2. Put `main.js`, `manifest.json`, and `styles.css` into `<your vault>/.obsidian/plugins/project-master/` (create it if needed — the folder **must** be named `project-master`);
3. Refresh community plugins in Obsidian settings and enable **Project Master**.

You can also add the repository `luna-jmy/ob-project-center` in [BRAT](https://github.com/TfTHacker/obsidian42-brat).

## Quick start

1. The default scan folder is `100 Projects` (changeable in settings): put your project notes there with `type: project` in frontmatter;
2. The minimum viable fields are `status` + `start_date` + `due_date` (see the [field reference](fields/));
3. Open the board via the ribbon icon or the command `Open project dashboard`.
