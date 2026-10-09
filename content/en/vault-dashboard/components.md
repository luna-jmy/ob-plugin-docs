---
title: Components
weight: 30
description: The 14 built-in components and the custom-script component
---

The workspace is assembled from component tiles. Below are all **14 built-in components** plus the **custom-script component**, grouped by purpose; parameters are filled in through the parameters panel in edit mode.

## Overview

| Component | Needs | In one line |
| --- | --- | --- |
| [Vault stats](#vault-stats) | — | 10 vault metrics, click to drill down |
| [Today's tasks](#todays-tasks) | — | Today / overdue / recently completed from your journal folder |
| [Quick jump](#quick-jump) | — | A filtered list of entry points to your notes |
| [Command buttons](#command-buttons) | — | Turn any Obsidian command into a button |
| [Quick create](#quick-create) | Templater | Create a note from a template in one click |
| [Dataview query](#dataview-query) | Dataview | Run a Dataview query inside the dashboard |
| [Recently created](#recently-created) | — | Notes created in the last N days |
| [Base view](#base-view) | Bases (Obsidian 1.9+) | Embed a `.base` view |
| [Random quote](#random-quote) | — | A random quote from your excerpts, with copy |
| [Year timeline](#year-timeline) | — | A full-year SVG axis with event flags |
| [Daily word change](#daily-word-change) | — | Net word gain/loss per day, last 30 days |
| [Writing heatmap](#writing-heatmap) | — | A GitHub-style activity heatmap |
| [Link stats chart](#link-stats-chart) | — | Trend line of internal links |
| [Structure analysis](#structure-analysis) | — | Note distribution across top-level folders |
| [Custom script](#custom-script-component) | opt-in | Render anything with a bit of JavaScript |

## Navigation & entry points

### Vault stats

Ten metrics to pick from: total notes, recently added, readable words, attachments, folders, links, orphans, broken links, empty notes, and short notes. **Click any number** to open the matching note list with keyword search (capped at 500 entries). The threshold for empty / short notes is a [setting](settings/).

"Broken links" counts notes whose body contains unresolved wiki / Markdown links (pointing at notes that don't exist); click to drill down into those notes.

{{< screenshot src="images/vault-dashboard/component-vault-stats.png" caption="The vault stats component" >}}

### Today's tasks

Scans daily notes in the journal folder and groups tasks into today / overdue / recently completed; click to jump to the exact line. Understands standard Markdown checkboxes plus Tasks-compatible emoji dates — see the [guide](usage/#todays-tasks). Read-only.

| Parameter | Default | Description |
| --- | --- | --- |
| Show recently completed `showCompleted` | on | Turn off to hide the "recently completed" section |

### Quick jump

A filterable list of note entry points, one click away.

| Parameter | Default | Description |
| --- | --- | --- |
| Limit `limit` | 8 | How many entries to show |
| Folder `folder` | empty | Restrict to a folder |
| Tag `tag` | empty | Restrict to a tag |
| Property `frontmatterKey` | empty | Filter by a frontmatter property |
| Value `frontmatterValue` | empty | Used together with the property name |

### Command buttons

Turns any Obsidian command (built-in or from other plugins) into a dashboard button; add as many as you like in edit mode, and optionally require a confirmation click for dangerous ones.

### Quick create

Creates notes from **Templater templates** in one click. Requires [Templater](https://github.com/SilentVoid13/Templater). Each button can configure:

- **Label**: the text on the button;
- **Template file**: path to the Templater template;
- **Folder** (optional): where the new note lands;
- **Filename pattern** (optional): supports the `{{date:format}}` placeholder, defaulting to `{{date:YYYY-MM-DD}}`; can also be combined with a **title**.

## Queries & embeds

### Dataview query

Renders a [Dataview](https://github.com/blacksmithgu/obsidian-dataview) query result inside the dashboard. Supports plain queries (TABLE / LIST / TASK / CALENDAR, …) and `dataviewjs` blocks (JS queries must be enabled in Dataview's settings).

| Parameter | Default | Description |
| --- | --- | --- |
| Query code `code` | empty | The query body (without \`\`\` fences) |
| Source note `source` | empty | The note providing query context; falls back to the active file |

### Base view

Embeds an Obsidian **Bases** view (requires Obsidian 1.9+). Its only parameter is the path to a `.base` file. It renders as a preview with an *Open* button that jumps to the full view.

### Recently created

Lists notes created in the last N days; click to open. The filters are the same as [Quick jump](#quick-jump) (folder / tag / property / value), plus:

| Parameter | Default | Description |
| --- | --- | --- |
| Days `days` | 30 | How far back to look |
| Limit `limit` | 20 | How many entries to show |

## Excerpts & timeline

### Random quote

Shows a random excerpt from the notes you point it at, with *copy* and *refresh* buttons — the copied format is "quote, blank line, — source". Source notes are expected to be named like 《Book Title》. Quotes are shown as plain text (inline Markdown is not rendered); candidate notes are collected by walking only the configured folder's subtree.

| Parameter | Default | Description |
| --- | --- | --- |
| Folder `folder` | empty | Folder holding your excerpt notes |
| Tag `tag` | empty | Tag that marks excerpt notes |

{{< screenshot src="images/vault-dashboard/component-random-quote.png" caption="The random quote component" >}}

### Year timeline

A full-year SVG axis: the 12 months are laid out proportionally to their real lengths, today carries an icon marker, and important dates can carry flags.

| Parameter | Default | Description |
| --- | --- | --- |
| Year `year` | 0 (this year) | Which year to show |
| Today icon `todayIcon` | 👩‍💻 | The emoji marking "today" |
| Events `events` | empty | A list where each entry has a **date** (`month-day`, e.g. `10-1`), a **title**, and an **icon** (default 🚩) |

{{< screenshot src="images/vault-dashboard/component-random-timeline.png" caption="The year timeline component" >}}

## Charts

The three chart components all rely on plugin-recorded snapshots; the part from before installation is **estimated** from file creation times, drawn in a distinct style, and can be hidden in settings.

### Daily word change

A bar chart of the **net** daily change in your vault's total word count over the last 30 days — bars up for words written, down for words removed. Hover for exact numbers.

### Writing heatmap

A GitHub-contribution-style heatmap where color depth encodes daily activity. On mobile it automatically uses the square (quarter-width) layout — no need to narrow the tile manually.

| Parameter | Default | Description |
| --- | --- | --- |
| Metric `metric` | 字数 (words) | What the heat encodes: words or new notes |

### Link stats chart

A trend line of the number of internal links (wiki and Markdown) in your vault.

| Parameter | Default | Description |
| --- | --- | --- |
| Range `range` | 365 | The window: 90 / 180 / 365 days |

### Structure analysis

Counts note distribution across top-level folders so you can see where your content actually lives.

| Parameter | Default | Description |
| --- | --- | --- |
| Show note count `showNotes` | on | Show the note count per folder |
| Show word count `showWords` | on | Show the total word count per folder |
| Show subfolder count `showSubfolders` | off | Show how many subfolders each top-level folder has |

## Custom script component

{{% notice style="warning" title="Security note" %}}
Scripts run with the plugin's access and can **read and write your vault**. Only run code you wrote yourself or have reviewed and trust. The feature is off by default.
{{% /notice %}}

If you write a little JavaScript, a script component can render anything — charts, aggregations, custom HTML.

**Getting started**

1. Turn on *Allow custom scripts* in settings;
2. Click *New script* — the plugin drops a starter template into the script folder (`.obsidian/plugins/vault-dashboard/data/`);
3. Edit the file, then back in the dashboard choose *Add*; the `script/<filename>` component appears at the bottom of the list.

**The contract**

The script declares its metadata in header comments:

```javascript
// cw:name=My component      // display name
// cw:icon=file-code         // icon (a Lucide icon name)
// cw:desc=A trusted local component   // description
// cw:param=title:text|Hello // parameter: key:type|default

const { container, params } = ctx;   // ctx provides the container and params
container.createEl("p", { text: String(params.title) });
```

- Parameters declared via `cw:param` show up in the edit-mode parameters panel;
- `ctx.container` is the component's render target (a standard HTMLElement) and `ctx.params` holds the user's values;
- Scripts re-run on every render — save the file and refresh the dashboard to see your changes.

{{< screenshot src="images/vault-dashboard/component-script.png" caption="A custom script component in action" >}}
