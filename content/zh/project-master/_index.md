---
title: Project Master
weight: 20
icon: fa-chart-gantt
description: 从项目笔记直接生成交互式甘特图
---

Project Master（项目管理中心）把你的项目笔记变成一块可交互的项目看板：左侧分组面板、右侧甘特图与 Mermaid 两个视图，拖拽调期、多维筛选、长期项目与里程碑一目了然。

数据全部来自笔记的 **frontmatter**——不引入数据库，也不要求改动你现有的项目笔记结构；甘特图与界面均为插件自绘，**不依赖任何其他插件**。

{{< screenshot src="images/project-master/main-view.png" caption="项目看板：左侧分组面板 + 右侧甘特图" >}}

## 功能亮点

- **自动识别项目**：扫描目录里 `type: project` 或带 `project` 标签的笔记自动上图，字段名还能在设置里整体映射成你自己的写法；
- **交互式甘特图**：拖拽改期（直接写回 frontmatter）、多级缩放、今天回位线、按状态 / 优先级着色；
- **分组面板**：按文件夹 / 状态 / 领域等分组，卡片可拖拽手动排序，支持「面板模式」整页当看板用；
- **多维筛选**：状态档（默认隐藏已完成 / 取消 / 归档）、领域、年份、优先级，可整块收起；
- **新建 / 编辑项目**：表单化新建（可选模板起步、自动归档到「资料」），点卡片即可编辑属性；
- **Mermaid 导出**：把甘特图导出为 Mermaid gantt 代码块写进笔记，或导出 SVG / JPG 图片；支持法定节假日排期、排除周末；
- **中英双语界面**，默认跟随 Obsidian。

## 安装

{{% notice style="info" title="环境要求" %}}
Obsidian **1.8.7** 及以上。
{{% /notice %}}

1. 到 [GitHub Releases](https://github.com/luna-jmy/ob-project-center/releases) 下载最新版本；
2. 把 `main.js`、`manifest.json`、`styles.css` 放进 `<你的 vault>/.obsidian/plugins/project-master/`（目录不存在就新建，**文件夹名必须是 `project-master`**）；
3. Obsidian「设置 → 第三方插件」刷新后启用 **Project Master**。

也可以用 [BRAT](https://github.com/TfTHacker/obsidian42-brat) 添加仓库 `luna-jmy/ob-project-center` 安装。

## 快速上手

1. 默认扫描目录是 `100 Projects`（可在设置改）：把项目笔记放进去，frontmatter 写上 `type: project`；
2. 最小可用字段只要 `status` + `start_date` + `due_date`（详见[笔记字段参考](fields/)）；
3. 点左侧栏图标或命令面板执行 `Open project dashboard` 打开看板。
