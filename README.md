# CUDA 并行编程完全指南

## 在线阅读

**<https://zhaojiew10.github.io/cuda-ebook/>**

网站由 GitHub Actions 自动构建并部署到 GitHub Pages，包含 6 个部分、54 章，支持章节目录、站内搜索和代码语法高亮。

## 项目简介

本项目使用 **MkDocs Material** 构建。章节正文为 Markdown，不再依赖 JavaScript 数据文件或 Canvas 动画。

## 本地启动

在项目根目录执行：

```bash
.venv/Scripts/python.exe -m pip install -r requirements.txt
.venv/Scripts/python.exe -m mkdocs serve
```

打开 <http://127.0.0.1:8000/cuda-ebook/> 即可阅读。按 `Ctrl+C` 停止手动启动的服务。

如需重新创建虚拟环境：

```bash
python -m venv .venv
.venv/Scripts/python.exe -m pip install -r requirements.txt
```

## 构建

```bash
.venv/Scripts/python.exe -m mkdocs build --strict
```

生成的网站位于 `site/`。构建后的线上首页地址为：

```text
https://zhaojiew10.github.io/cuda-ebook/
```

## 目录结构

```text
docs/
  index.md                       电子书首页及章节目录
  chapters/                      54 个 Markdown 章节
  resources/                     章节图片
mkdocs.yml                       MkDocs Material 配置及导航
requirements.txt                 构建依赖
.github/workflows/deploy.yml     GitHub Pages 部署工作流
```

## 发布到 GitHub Pages

仓库 Pages 配置位于：

<https://github.com/zhaojiew10/cuda-ebook/settings/pages>

**Build and deployment → Source** 应选择 **GitHub Actions**。如果未启用 Pages，`actions/configure-pages` 会报 `Get Pages site failed` / `HttpError: Not Found`。

推送到 `main` 分支后，`.github/workflows/deploy.yml` 会自动构建并发布到 **<https://zhaojiew10.github.io/cuda-ebook/>**。
