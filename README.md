# ob-plugin-docs — 插件文档站（Hugo）

全部 Obsidian 插件的**用户文档站**（公开仓，GitHub Pages 部署），Hugo 构建，**中英双语**
（`content/zh/` 与 `content/en/` 同路径互为翻译，语言键 `zh-cn` / `en`，头部自动生成语言切换）。

> 2026-10-01 从私有共享仓 ob-tdk-general 的 `docs/` 目录迁入（私有仓不能用 GitHub Pages）。
> 站点与内容维护规则随仓迁移，工程约束仍以工作区唯一 agent 文档为准。

**并排双主题**（git 子模块，`--theme` 参数一键切换，内容/菜单/自定义样式两主题共用）：

- [Blowfish](https://github.com/nunocoracao/blowfish)（`config/_default/hugo.toml` 里的默认主题，**线上部署用它**）
- [Hextra](https://github.com/imfing/hextra)

## 部署（GitHub Actions）

推 `main` 即自动构建部署；工作流见 `.github/workflows/hugo.yml`。

- **首次部署前**：仓库 Settings → Pages → Source 选 **GitHub Actions**（一次性设置），
  之后到 Actions 页 Run workflow（或随便再推一笔）触发首部署；
- 线上地址：`https://luna-jmy.github.io/ob-plugin-docs/`（根路径自动跳 `zh-cn/`）；
- **baseURL 由 CI 注入**（`configure-pages` → `hugo --baseURL`），因此
  `config/_default/hugo.toml` 里的 `baseURL = "/"` 是给本地预览留的，两边互不干扰；
- CI 构建默认主题 Blowfish；切主主题 = 改 `hugo.toml` 的 `theme` 字段，工作流无需动。
  （若切到 Hextra 长期部署，注意它构建时要从 jsdelivr 拉 flexsearch，CI 网络无代理、
  `hugo.toml` 的 `[security.http]` 放行列表已覆盖 jsdelivr。）

## 常用命令（本地）

```bash
hugo                          # 构建（默认主题 Blowfish）→ public/
hugo --theme hextra           # 用 Hextra 构建（可加 --destination public-hextra/ 并行对比）
hugo server                   # 本地预览（默认 Blowfish）http://localhost:1313
hugo server --theme hextra    # 本地预览 Hextra
```

双主题**并排对比**（两个端口各开一个标签页，都渲染在内存里、互不写盘）：

```bash
hugo server --theme hextra --port 1313 --renderToMemory   # Hextra   → http://localhost:1313
hugo server --port 1314 --renderToMemory                  # Blowfish → http://localhost:1314
```

> ⚠️ Hugo 0.167 的 `hugo server` 默认 "Serving pages from disk"（页面渲染进 `public/`）。
> 若预览的同时又跑 `hugo --destination public` 静态构建，后者会**覆盖同一目录**，预览页就被换成另一次构建的产物。
> 预览期间要跑静态构建时，server 记得加 `--renderToMemory`。

Windows 下刚装完 Hugo 记得重开终端（或手动刷新 PATH）。
需要 **Hugo extended** ≥0.146（两个主题都要求；主题声明的兼容区间可能略落后于最新 Hugo 版本，超出时仅警告、构建照常）。
Hextra 构建时从 jsdelivr 拉 flexsearch 搜索库（结果会缓存）；`hugo.toml` 的 `[security.http]` 已放行本机代理 fake-IP 网段，否则首次构建会被安全策略拦下。

## 结构约定

```
config/_default/                 站点配置（Hugo 分文件结构，两主题参数共存于 params.toml）
  hugo.toml                      全局：默认主题、双语、输出格式、安全放行
  languages.zh-cn.toml / .en.toml 各语言：标题、作者、contentDir
  menus.zh-cn.toml / menus.en.toml 各语言：头部导航（4 插件 + GitHub，两主题共用一份）
  params.toml                    主题参数：Blowfish 与 Hextra 各自的小节互不干扰
  markup.toml                    渲染设置（两主题共同要求）
content/zh/<插件>/…               中文文档
content/en/<插件>/…               英文文档（路径与中文一一对应）
layouts/shortcodes/screenshot.html  截图占位 shortcode（主题无关）
layouts/shortcodes/notice.html     提示框 shortcode（本地实现，主题无关）
assets/css/custom.css            站点自定义样式（两个主题都会自动加载）
static/images/<插件>/…            截图存放处（见下）
themes/blowfish                  主题子模块（勿手改）
themes/hextra                    主题子模块（勿手改）
```

## 截图约定（占位 → 实图）

正文里用 shortcode 预留截图位：

```markdown
{{</* screenshot src="images/vault-dashboard/main-view.png" caption="主界面" */>}}
```

- 截图文件**还没放**时，页面显示虚线占位框（含期望路径）；
- 把 png/jpg 放进 `static/images/<插件>/` 对应路径后，**同一写法自动变成真图**，无需改文档；
- en 侧 caption 用英文，zh 侧用中文。

## 写作规则

1. **以源码为准**：文档描述的行为必须能在对应插件仓的源码里找到依据；改完功能先改文档再发布。
2. **双语成对**：新增/修改中文页必须同步英文页，路径一致。
3. **每个插件一个小节**（section `_index.md` + usage / settings / faq 子页）；新插件立项发布时在此登记并在两侧 `content/` 建目录、两份 `menus.*.toml` 加导航项。
4. 界面文案的英文译名优先沿用各仓 `src/i18n/en.ts` 的既有翻译，保持站内与插件内说法一致。
