---
title: Settings
weight: 40
description: Period tabs, global settings, defaults
---

Open via: Obsidian settings → Community plugins → **Quick Journal**.

## Period tabs (day / week / month / quarter / year)

Five tabs with the same structure, independently configured:

| Setting | Default (daily shown) | Description |
| --- | --- | --- |
| Folder | `500 Journal/540 Daily` | Where that period's journals live (weekly `530 Weekly`, monthly `520 Monthly`, quarterly `515 Quarterly`, annual `510 Annual`) |
| Filename format | `YYYY-MM-DD` | moment format (weekly `YYYY-[W]ww`, monthly `YYYY-MM`, quarterly `YYYY-[Q]Q`, annual `YYYY`) |
| Template note | empty | The template path read by *Template detection* |
| Show summary tab | On | When off, that period's tab disappears from the summary toolbar (at least one of week / month / quarter / year stays on; not present on the daily tab) |
| Sections | five daily ones (see the [guide](usage/#the-six-section-types)) | Per section: heading, type, fields (key / label / unit), line template, series marker & label (compare), timestamp flag, panel flag |

Which fields a section offers depends on its type: check-in / data / text sections take inline fields, list sections a line template, paragraphs need none. A compare section additionally configures two **series** (emoji marker + label); the keys written in the note are base key + series marker.

## Global settings

| Setting | Default | Description |
| --- | --- | --- |
| Language | Follow Obsidian | Chinese / English |
| Summary open location | Tab | The journal summary opens in a tab or the right sidebar |
| Panel open location | Tab | The quick panel likewise |
| Show completed tasks | Off | Persistent toggle for the panel and the summary |
| Include non-daily tasks | Off | Whether task charts / heatmaps count tasks outside the journal folders |
| Task markers: open / done / cancelled / non-task | `[ ]` / `x` / `-` / … | The bracket markers used to recognize task lines |
| Unfinished marker | space + `>` | The marker recognizing unfinished tasks for the rollover button |
| Auto timestamp | Off | Whether new panel entries get a timestamp automatically |
| Trend field | empty | The field selected by default in the data-trend component |
| Summary queries | empty | The query blocks entered manually into the layout (title + code), maintained in edit mode |
| Reset to defaults | — | One click resets **all plugin configuration** (notes untouched) |

## Summary layout

Maintained in edit mode (the summary view's toolbar gear): drag-reorder, delete, and add components; the layout and query list live in the plugin data and reset with it.
