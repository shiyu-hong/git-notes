# Git 笔记

一个用 Quarto book 组织的中文 Git 个人笔记（面向 Windows 用户，从环境配置到 GitHub Pages 发布）。写作本项目的任何内容前，加载 `quarto-book-zh` skill 并以其 SKILL.md 为准；作家角色以 `_meta/persona.md` 为唯一权威来源（SSOT），不存在时先询问用户选择角色再创建。

## 命令

- 验证构建：`quarto render`。修改结构、内容或 `_quarto.yml` 后**自动运行**，不要询问；失败则修复后重跑。
- 实时预览：`quarto preview`（本地服务器，浏览器查看整本书，保存自动重渲染）。
- 只渲染单文件：`quarto render chapters/<章节路径>.qmd`。

## 目录结构

- `index.qmd` —— 书根首页（欢迎语 + 章节导航表），必须位于根目录并命名为 `index.qmd`。
- `chapters/` —— 章节源文件。`chapters/preface/index.qmd` 是前言，放在首页之后、第一个 part 之前，用 `# 前言 {.unnumbered}` **不编号**。
- `_quarto.yml` —— book 配置；`theme` 引用 `_assets/theme.scss`（日夜主题 cosmo/darkly），`output-dir: docs`。
- `_meta/persona.md` —— 作家角色 SSOT（本项目为 Git 专家）。
- `_assets/theme.scss` —— 全部主题定制；修改用 Bootstrap SCSS 变量（如 `$font-size-base`，不是 `$font-size-root`）。
- `docs/`、`.quarto/` —— 构建产物，**禁止编辑**，内容以 `quarto render` 生成为准。

## 写作规范

- 简体中文；专有名词无通用译名才保留英文（Quarto、GitHub、YAML 等）。
- 面向读者，用「你」；开场一句话点明内容，不做自我评价，正文不出现「专家」「大牛」等自我标榜词。
- 命令块用 ```bash（不加 `$` 提示符）；命令输出块**不加语言标注**；配置文件按实际格式标注（yaml/json/toml）。
- 单行短条目用**紧凑列表**（条目间不空行）；条目含多段文字/代码块/嵌套列表时才空行。
- 链接用短文案 `[文案](url)`；仓库内文件一律用相对路径。
- 结构改动（chapters 顺序、part、前言）后必须确认编号：前言不编号、正文章节编号不出现 `0.x` 之类断号。

## 提交与 PR

- 未经明确要求不 commit、不 push、不开 PR。
- 提交信息用命令式简短中文，聚焦改动影响，不写实现细节。
- 绝不提交密钥、凭据或 token；不把生成产物（`docs/`）纳入版本控制。

## 边界

**先询问**：

- 重构章节目录结构、调整 part 分组。
- 切换主题、配色或字体（涉及 `_assets/theme.scss` 全局改动）。
- 修改书名、副标题或章节覆盖范围。
- 升级 Quarto/skill 依赖或引入新格式（PDF、EPUB 等）。

**禁止**：

- 编辑 `docs/`、`.quarto/` 等构建产物（用 `quarto render` 重新生成）。
- 添加代码注释、表情符号等与本书无关的内容。
- 未经要求执行 git 提交/推送等写操作。
- 覆盖、重写或删除用户已有内容而不先确认。
