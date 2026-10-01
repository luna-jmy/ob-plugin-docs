---
title: Vault Dashboard
weight: 10
icon: fa-gauge-high
description: 把 vault 变成「打开就能开工」的主页
---

Vault Dashboard（仓库工作台）把整个仓库汇总成一个可自由拼装的主页：打开 Obsidian 即见统计、今日任务与常用入口，不必先想「今天从哪个文件开始」。

页面由一个个**组件块**组成——统计、任务、跳转、图表各有独立方块，位置与宽度随意调整，全部配置即时保存在本地。

{{< screenshot src="images/vault-dashboard/main-view.png" caption="工作台主界面（默认布局：统计 + 今日任务 + 快速跳转 + 命令按钮）" >}}

## 功能亮点

- **14 种内置组件**：仓库统计、今日任务、快速跳转、命令按钮、快速新建、Dataview 查询、最近创建、Bases、随机书摘、年度时间线、字数趋势、活跃热力图、链接趋势、目录结构；
- **四档宽度自由排版**：每个组件可占 25% / 33% / 50% / 100% 宽度，网格自动换行；
- **只读的工作台模式**：统计可点击下钻、任务点击即跳转原文，但不会误改你的笔记；
- **历史趋势**：记录仓库快照，绘制字数与笔记数趋势、活跃热力图；装插件之前的历史按文件创建时间估算；
- **可选集成**：Templater、Dataview、Bases 装了自动增强，没装不影响其他组件；
- **自定义脚本组件**（默认关闭）：会写代码的话，可以用一个小脚本渲染任意内容。

## 安装

{{% notice style="info" title="环境要求" %}}
Obsidian **1.8.7** 及以上。
{{% /notice %}}

**方式一：BRAT（推荐）**

1. 安装社区插件 [BRAT](https://github.com/TfTHacker/obsidian42-brat)；
2. BRAT 设置 → `Add Beta plugin` → 填入 `luna-jmy/ob-workspace`；
3. 在「第三方插件」列表中启用 **Vault Dashboard**。

**方式二：手动安装**

1. 从 [GitHub Releases](https://github.com/luna-jmy/ob-workspace/releases) 下载最新版的 `main.js`、`manifest.json`、`styles.css`；
2. 放入 `.obsidian/plugins/vault-dashboard/`（没有就新建）；
3. 重启 Obsidian，在「第三方插件」中启用。

## 依赖说明

| 依赖 | 是否必需 | 用途 |
| --- | --- | --- |
| 无 | ✅ 必需（即零依赖） | 全部核心组件开箱即用 |
| [Templater](https://github.com/SilentVoid13/Templater) | 可选 | 「快速新建」组件调用 Templater 模板建笔记 |
| [Dataview](https://github.com/blacksmithgu/obsidian-dataview) | 可选 | 「Dataview 查询」组件执行 TABLE / LIST / TASK / CALENDAR 查询与 dataviewjs |
| Obsidian Bases（1.9+ 内置） | 可选 | 「Bases」组件嵌入 base 视图 |

## 快速上手

1. 启用插件后，点击左侧栏的**房子图标**（或命令面板执行「打开工作台」）；
2. 默认布局已经可用：仓库统计、今日任务、快速跳转、命令按钮；
3. 想调整？执行命令「切换编辑模式」，即可添加 / 删除组件、改宽度与参数——详见[使用指南](usage/)。
