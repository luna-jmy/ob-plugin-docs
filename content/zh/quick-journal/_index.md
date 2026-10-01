---
title: Quick Journal
weight: 40
icon: fa-pen-nib
description: 移动优先的日志速记：表单录入 + 内容流 + 周月年汇总
---

Quick Journal（日志速记）让记日志这件事变得极轻：点一个按钮、填一个表单，打卡、数据、小结直接写进当天日志的对应标题区——**全程不进 Markdown 编辑模式**，手机上单手可完成。周 / 月 / 年的汇总视图与复盘笔记也在同一套体系里。

日志笔记仍是普通 Markdown：标题区 + 内联字段（`字段:: 值`），插件读它、写它，别的工具也认它。

{{< screenshot src="images/quick-journal/quick-capture.png" caption="快速录入表单" >}}

## 功能亮点

- **五种标题区**：打卡（✔️/❌ 开关）、数据（数值字段）、文本（一句话小结）、列表（逐项追加，可配行模板记任务）、段落（一天一条长文）——设置里完全自定义；
- **三个入口**：快速录入（每区还有独立命令可绑快捷键）、类 Thino 的**速记面板**内容流、**日志汇总**仪表盘；
- **多期间**：日 / 周 / 月 / 年各自目录、文件名格式与标题区配置；周 / 月 / 年复盘就是对应期间下的文本标题区；
- **模板识别**：填一下模板笔记路径，标题区配置按模板自动重建；
- **自动建笔记**：目标日志不存在时按配置生成骨架，录入永不被「还没建今天的笔记」打断；
- **汇总视图组件化**：任务图、打卡汇总、数据趋势、月历、热力图、最近速记、查询块自由拼装，图表全部原生自绘；
- **中英双语界面**，默认跟随 Obsidian。

## 安装

{{% notice style="info" title="环境要求" %}}
Obsidian **1.8.7** 及以上。
{{% /notice %}}

**方式一：BRAT（推荐）**

1. 安装社区插件 [BRAT](https://github.com/TfTHacker/obsidian42-brat)；
2. BRAT 设置 → `Add Beta plugin` → 填入 `luna-jmy/ob-quick-journal`；
3. 在「第三方插件」列表中启用 **Quick Journal**。

**方式二：手动安装**

从 [GitHub Releases](https://github.com/luna-jmy/ob-quick-journal/releases) 下载 `main.js`、`manifest.json`、`styles.css`，放进 `.obsidian/plugins/quick-journal/` 后启用。

## 依赖

**无需任何其他插件**——解析、统计、界面全部插件内实现。Dataview 为可选增强：汇总视图里手动添加的 `dataview` / `dataviewjs` 查询块由它渲染（不装则显示提示）。

## 快速上手

1. 启用插件，点左侧栏图标（或命令「打开快速录入」）；
2. 默认配置对齐现行体系：日志在 `500 Journal/540 Daily`（日）、`530 Weekly`（周）、`520 Monthly`（月）、`510 Annual`（年），每日默认五个标题区（打卡 / 数据 / 小结 / GTD 任务 / 灵感）；
3. 选标题区 → 填表单 → 提交，内容就落在今天日志的对应位置。想改成自己的结构？去设置里改标题区，或用[模板识别](usage/#从模板识别)一键重建。
