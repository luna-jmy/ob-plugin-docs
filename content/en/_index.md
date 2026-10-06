---
title: Plugins
description: Local-first, bilingual Obsidian plugins
weight: 1
type: docs # Hextra: docs layout (with left sidebar)
cascade:
  type: docs
---

This site hosts the documentation for the Obsidian plugins that accompany [ThinkDoKit](https://ppxyd.xin). They share the same principles:

- **Fully local** — no network requests, no telemetry, no accounts; your data stays in your vault and the plugin folder;
- **Bilingual UI** (Chinese / English) that follows your Obsidian language by default, with a manual override in each plugin's settings;
- **Zero required dependencies** — a few components integrate optionally with Templater / Dataview / Bases and degrade gracefully when they are missing;
- **MIT licensed** — see each repository for the source.

## Plugins

### [Vault Dashboard](vault-dashboard/)

Turns your whole vault into a start page you can open and immediately work from: stats, today's tasks, quick jump, trends and heatmaps, 14 built-in components to arrange freely, plus an optional custom-script component.

### [Project Master](project-master/)

An interactive Gantt chart generated straight from your project notes: drag to reschedule, multi-dimensional filters, long-term projects and milestones, Mermaid export.

### [Task Matrix](task-matrix/)

See every task in one view: list / GTD / four-quadrant / calendar / Gantt. Matrix layout focuses on *important × urgent*. Plain-text task syntax — your data is never locked in.

### [Quick Journal](quick-journal/)

A mobile-friendly journaling workflow: form-based quick capture, a desktop quick panel, and weekly / monthly / yearly summaries — check-ins, tracked numbers, and a task board in one note.

## Installation

Every plugin can be installed in two ways (see the *Install* section of each manual):

- **BRAT**: add the plugin's GitHub repository in [BRAT](https://github.com/TfTHacker/obsidian42-brat) to receive beta updates;
- **Manual**: download `main.js` / `manifest.json` / `styles.css` from GitHub Releases, drop them into `.obsidian/plugins/<plugin id>/`, and enable the plugin in settings.

## Feedback

Issues are welcome in each plugin's repository — bug reports, feature ideas, and translation polish all count.
