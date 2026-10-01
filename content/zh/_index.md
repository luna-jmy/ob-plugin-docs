---
title: 插件总览
description: 纯本地、中英双语的 Obsidian 插件集
weight: 1
type: docs # Hextra：走 docs 布局（带左侧导航栏）；Blowfish 无此目录，自动回退默认布局
cascade:
  type: docs
---

这里收录 Luna 开发的全部 Obsidian 插件。它们共用同一套原则：

- **纯本地运行**——无网络请求、无遥测、无账号，数据只存在你的 vault 与插件目录里；
- **界面中英双语**，默认跟随 Obsidian 语言，也可在各自设置里手动指定；
- **主体功能零依赖**，个别组件支持与 Templater / Dataview / Bases 等热门插件可选集成，缺失时自动降级并给出提示；
- **MIT 开源**，源码见各插件仓库。

## 插件一览

### [Vault Dashboard — 仓库工作台](vault-dashboard/)

把整个 vault 变成「打开就能开工」的主页：统计、今日任务、快速跳转、趋势图与热力图，14 种内置组件自由拼装，另有可选的自定义脚本组件。

### [Project Master — 项目管理中心](project-master/)

从项目笔记直接生成交互式甘特图：拖拽调期、多维度筛选、长期项目与里程碑、Mermaid 导出，管理节奏一目了然。

### [Task Matrix — 任务仪表盘](task-matrix/)

一个视图看全部任务：列表 / GTD / 四象限 / 日历 / 甘特五视图切换，矩阵布局聚焦「重要 × 紧急」，纯文本任务语法、不锁数据。

### [Quick Journal — 日志速记](quick-journal/)

移动端友好的日志工作流：表单化快速录入、桌面速记面板、按周 / 月 / 年汇总，打卡、数据记录、任务看板一段笔记全搞定。

## 安装

各插件均提供两种安装方式（详见各自文档的「安装」小节）：

- **BRAT**：在 [BRAT](https://github.com/TfTHacker/obsidian42-brat) 中添加对应 GitHub 仓库，可接收 Beta 更新；
- **手动安装**：从 GitHub Releases 下载 `main.js` / `manifest.json` / `styles.css`，放入 `.obsidian/plugins/<插件 id>/` 后在设置中启用。

## 反馈与问题

每个插件仓库的 Issues 都欢迎反馈：使用问题、功能建议或翻译润色均可。
