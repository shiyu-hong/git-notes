# Git 笔记

一本面向 Windows 用户的中文 Quarto book，从 Git 环境配置到 GitHub Pages 发布，按步骤组织的个人笔记。

## 章节

| 章节 | 内容 |
|------|------|
| [前言](chapters/preface/index.qmd) | 关于本笔记、前置条件与阅读建议 |
| [环境配置](chapters/setup/install-windows.qmd) | 安装 Git 并完成初始配置（身份、换行符、SSH） |
| [日常使用](chapters/daily/commit.qmd) | Git 日常指令：提交、撤销、分支、推送同步 |
| [平台用法](chapters/platforms/gerrit.qmd) | Gerrit、GitLab 等平台上的 Git 特殊用法 |
| [Quarto 发布与部署](chapters/quarto-publish/github-pages.qmd) | 用 GitHub Actions 构建并发布 Quarto book 到 GitHub Pages |

首页在根目录 `index.qmd`，章节位于 `chapters/` 下。

## 本地构建

```bash
quarto render
```

构建产物输出到 `docs/` 目录。

## 本地预览

```bash
quarto preview
```

## 发布

推送到 `main` 分支后，GitHub Actions 会自动构建并发布到 GitHub Pages。首次使用需在仓库 Settings → Pages 中设置 Source 为 `gh-pages` 分支。
