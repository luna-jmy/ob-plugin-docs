---
title: Task Matrix
weight: 30
icon: fa-table-cells
description: 列表 / GTD / 四象限 / 日历 / 甘特五视图的任务仪表盘
---

Task Matrix（任务矩阵）把 vault 里所有任务汇成一块可视化仪表盘：**列表、GTD、四象限（艾森豪威尔矩阵）、日历、甘特图**五种视图随意切换，筛选、拖拽、新建、编辑一应俱全。

任务就是你笔记里普通的 Markdown 复选框——插件不改格式、不建数据库，你在任何笔记里写的任务都会自动出现；在仪表盘里勾选、改期、改优先级，写回的也还是那一行 Markdown。

{{< screenshot src="images/task-matrix/main-view.png" caption="四象限视图：重要 × 紧急" >}}

## 功能亮点

- **五种视图**：列表（按笔记浏览）、GTD（收件箱 / 进行中 / 等待 / 完成）、四象限、日历（月 / 周 / 列表）、甘特图（日 / 周 / 月 / 年时间轴）；
- **纯文本任务语法**：`📅` 截止、`🛫` 开始、`🔺` 关键……与 Tasks 生态的表情标记兼容，另有 Dataview 风格的 `[due:: …]` 行内字段写法；
- **任务卡操作**：完成 / 重开 / 开始 / 取消 / 编辑 / 删除，四象限与 GTD 里还有快捷移动按钮；
- **拖拽改状态**：把卡片拖到 GTD 列或象限里，插件写回对应的标签与日期；
- **多维筛选**：搜索、状态、标记、日期区间、排序，实时显示「命中 / 总数」；
- **甘特 + Mermaid**：时间轴视图可预览并导出 Mermaid 代码、SVG / JPG 图片，支持节假日排期；
- **中英双语界面**，默认跟随 Obsidian。

## 安装

{{% notice style="info" title="环境要求" %}}
Obsidian **1.5.0** 及以上。
{{% /notice %}}

**方式一：BRAT（推荐）**

1. 安装社区插件 [BRAT](https://github.com/TfTHacker/obsidian42-brat)；
2. BRAT 设置 → `Add Beta plugin` → 填入 `luna-jmy/obsidian-task-matrix`；
3. 在「第三方插件」列表中启用 **Task Matrix**。

**方式二：手动安装**

1. 从 [GitHub Releases](https://github.com/luna-jmy/obsidian-task-matrix/releases) 下载 `main.js`、`manifest.json`、`styles.css`；
2. 在 `.obsidian/plugins/` 下新建文件夹（**必须叫 `task-matrix-dashboard`**）并放入三个文件；
3. 在「第三方插件」中启用 **Task Matrix**。

**方式三：源码构建**

```bash
git clone https://github.com/luna-jmy/obsidian-task-matrix.git
cd obsidian-task-matrix
npm install && npm run build
```

把产出的三个文件复制进 `.obsidian/plugins/task-matrix-dashboard/`。

## 依赖

**无需任何其他插件**——只用 Obsidian 自身 API，所有视图均为插件自绘。唯一一处可选集成：日志模板里的 Templater `<% … %>` 命令，在插件新建目标笔记时由 Templater（若安装）展开；没装则原样复制，`{{title}}` / `{{date}}` 变量照常生效。

## 快速上手

1. 启用插件，点左侧栏**看板图标**（或命令面板执行「打开任务矩阵」）；
2. 默认扫描 `500 Journal` 与 `100 Projects` 两个目录——在设置里改成你放任务的目录（留空则扫全库）；
3. 在任意笔记里写 `- [ ] 买牛奶 📅 2026-10-02`，刷新后它就在仪表盘里了；语法详见[任务语法](syntax/)。
