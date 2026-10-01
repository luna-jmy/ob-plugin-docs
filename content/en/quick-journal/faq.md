---
title: FAQ & Limitations
weight: 50
description: Data, privacy, and known limits
---

## FAQ

**What does a journal look like?**

Plain Markdown: heading sections + inline fields (`field:: value`) + list lines. The plugin writes only under the heading you explicitly submit to — and anything you write by hand or with another plugin reads back just the same.

**Where do unchecked check-ins go?**

Nowhere — unchecked fields are not written. Journals keep only what you actually checked; "not done" appears as the *unrecorded* segment in the summary's ratio bars instead of cluttering your notes.

**Why don't query blocks render?**

They're delegated to Dataview: install and enable it (dataviewjs additionally needs JS queries enabled in Dataview's settings). Everything else works without it.

**What is the unfinished-task rollover?**

A button at the top of the quick panel: it carries still-unfinished task lines from the **previous period's** journal into today's, so daily tasks roll forward naturally without manual copying.

**I want a different journal structure — do I reconfigure everything?**

No. Fill in the template note path in settings and click *Template detection*; the section config rebuilds from the template. Display names can be tweaked afterwards.

## Data & privacy

Fully local: no network requests, no telemetry, no accounts, no external services. Writes happen only inside the journal notes you explicitly submit to; configuration lives in the plugin's data file. *Reset to defaults* clears configuration only — never a note.

## Known limitations

- the week starts on **Monday** (matching the current template's ISO-week convention); no setting for it yet;
- mobile is the primary design target, but not every item has been verified on every device (see the "unverified" notes in the CHANGELOG);
- query blocks support `dataview` / `dataviewjs` only (the early Tasks-query support was removed).
