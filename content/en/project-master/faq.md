---
title: FAQ & Limitations
weight: 50
description: Common questions, data safety, known limits
---

## FAQ

**Why are some projects missing from the Gantt chart?**

The top of the view states the reason and count. Usually one of two: ① both dates are missing (and the fallback is set to "leave off the chart"); ② it's a long-term project (`long-term: true`) — those never appear on the chart, only in the left panel.

**Cancelled projects are still on the chart?**

Deliberate: a cancellation is part of a project's history. To focus on active work, use the status presets in the filter bar (the default preset hides completed / cancelled / archived together).

**Does dragging modify my notes?**

Yes — on release, the new dates are written back to the note's `start_date` / `due_date` frontmatter (per your field mapping). That's both the cost and the benefit of "the chart and the notes are one source": there is no second copy of the data and nothing to sync.

**Does it understand Chinese status values?**

Yes. Chinese-alias compatibility is on by default — 执行中, 完成, and friends are read as `active`, `completed`, and so on; you can extend the aliases in settings.

**What if a folder holds several project notes?**

The group picks a representative: the note with `main-project: true` if any, otherwise the first one; more than one note with no flag raises a "multiple projects" hint. One main note per project folder is the recommended pattern.

## Data & privacy

- The plugin only reads and writes your notes' frontmatter and its own settings file; it makes **no network requests** — no telemetry, no accounts, no paywall;
- the Gantt chart and the whole UI are self-drawn — **no dependency on Dataview, Templater, or any other community plugin**.

## Known limitations

- Mermaid export does not support per-task colors (a Mermaid limitation);
- Gantt drag-rescheduling is **disabled on mobile** (it conflicts with touch scrolling) — edit dates through the dialog there;
- detection covers the scan folders only; project notes outside them never appear.
