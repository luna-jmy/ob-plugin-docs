---
title: Settings
weight: 40
description: Every setting and its default
---

Open via: Obsidian settings → Community plugins → **Vault Dashboard**. Every change takes effect and is saved immediately.

| Setting | Default | Description |
| --- | --- | --- |
| Language | Follow Obsidian | Follow Obsidian / Chinese / English |
| Density | Comfortable | Comfortable / compact — padding and font size inside tiles |
| Open on startup | On | Open the workspace automatically when Obsidian starts |
| Open behavior | New tab | New tab / replace current tab |
| Journal folder | empty | The diary folder scanned by [Today's tasks](components/#todays-tasks), e.g. `500 Journal`; the component stays empty until this is set |
| Date format | `YYYY-MM-DD` | [moment format](https://momentjs.com/docs/#/displaying/format/) used to parse daily-note filenames; must match them (`YYYY-MM-DD` ↔ `2026-10-01.md`) |
| Excluded folders | empty | Comma-separated folders left out of stats and history. **Changing this rebuilds all history** — scopes must not mix, or trends show fake jumps |
| Empty/short threshold | 10 | Notes with fewer words than this count as "short" |
| Recent days | 7 | Look-back window (days) for "recently completed" tasks and recent lists |
| Show estimated history | On | Whether trend charts include the estimated pre-installation segment |
| Allow custom scripts | **Off** | Required before adding [custom-script components](components/#custom-script-component) |
| Script folder | (read-only) | Where scripts live: `.obsidian/plugins/vault-dashboard/data/`; *New script* generates a starter template |
| Clear history | — | Manually wipes all history snapshots (layout and settings are kept) |

## Where the data lives

- **`data.json`** (in `.obsidian/plugins/vault-dashboard/`): settings, workspace layout, and history snapshots, all in one file;
- **the `data/` subfolder**: your custom scripts.

Both live inside the plugin folder: they don't sync with your notes (unless you sync the whole `.obsidian` folder) and are removed when you uninstall the plugin — back them up before moving machines or reinstalling. See the [FAQ](faq/).
