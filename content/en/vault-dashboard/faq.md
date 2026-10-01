---
title: FAQ & Limitations
weight: 50
description: Data, privacy, compatibility, and known limits
---

## Data & backup

**Where is plugin data stored?**

Entirely inside the plugin folder (`.obsidian/plugins/vault-dashboard/`): `data.json` holds settings, layout, and history snapshots; the `data/` subfolder holds custom scripts. The plugin never writes to your notes.

**New computer / reinstall?**

These files don't travel with your notes. Back up both paths and restore them in the new environment to get everything back; skipping the backup costs you only your layout and history — your notes are untouched.

**When are snapshots recorded?**

On demand, whenever a chart component renders — one snapshot per day; opening the dashboard repeatedly on the same day only updates that day's entry. Days you never opened the workspace have no real snapshot and are filled in by estimation.

## Privacy

Fully local: no network requests, no telemetry, no accounts. The only code-execution path is the custom-script component you must enable by hand — see the [security note](components/#custom-script-component).

## FAQ

**Why can't I check tasks off?**

*Today's Tasks* is read-only by design: task state lives in the checkboxes in your notes — Obsidian and plugins like Tasks own the checking; the dashboard only aggregates and jumps. Clicking a task opens the note on that exact line.

**The stats don't match what I expected?**

Check three things: ① folders in *Excluded folders* are not counted; ② stats cover Markdown notes, with attachments counted separately; ③ "short notes" depend on the *empty/short threshold* setting.

**"Today's tasks" shows nothing?**

Make sure the *journal folder* setting is filled in and that the daily notes inside are named so they parse with your *date format* (e.g. `2026-10-01.md` for `YYYY-MM-DD`).

**A tile says it needs another plugin?**

The optional-integration components depend on: Quick create → Templater, Dataview query → Dataview, Base view → Obsidian 1.9+ Bases. Install the dependency and the tile starts working — no restart needed.

## Known limitations

- The desktop app is the primary test environment; the plugin installs and runs on mobile but has not been verified device by device;
- Drill-down lists are capped at 500 entries;
- History granularity is one day, and pre-installation segments are estimates;
- The plugin was formerly named custom-workspace and was renamed at 0.2.0 — if you're coming from the old version, uninstall it and follow the [install steps](../#install) (the old `data.json` is not migrated).
