# CUDA 并行编程完全指南

本项目使用 **MkDocs Material** 构建，包含 6 个部分、54 章。章节正文为 Markdown，不再依赖 JavaScript 数据文件或 Canvas 动画。

## 本地启动

在项目根目录执行：

```bash
.venv/Scripts/python.exe -m pip install -r requirements.txt
.venv/Scripts/python.exe -m mkdocs serve
```

访问：

- 电子书：<http://127.0.0.1:8000/cuda-ebook/>
- 根路径 <http://127.0.0.1:8000/> 会自动跳转到电子书。

按 `Ctrl+C` 停止手动启动的服务。

如需重新创建虚拟环境：

```bash
python -m venv .venv
.venv/Scripts/python.exe -m pip install -r requirements.txt
```

## 构建

```bash
.venv/Scripts/python.exe -m mkdocs build --strict
```

生成的网站位于 `site/`。

## 目录结构

```text
docs/
  index.html                     根路径跳转页
  cuda-ebook/
    index.md                     电子书目录
    chapters/                    54 个 Markdown 章节
    resources/                   章节图片
mkdocs.yml                       MkDocs Material 配置及导航
requirements.txt                 构建依赖
.github/workflows/deploy.yml     GitHub Pages 部署工作流
```

## 发布到 GitHub Pages

首次部署前，必须打开仓库的 **Settings → Pages → Build and deployment → Source**，选择 **GitHub Actions**：

<https://github.com/zhaojiew10/cuda-ebook/settings/pages>

如果未启用 Pages，`actions/configure-pages` 会报 `Get Pages site failed` / `HttpError: Not Found`。该步骤不能仅通过修改 Markdown 或工作流文件代替。

推送到 `main` 分支后，`.github/workflows/deploy.yml` 会自动构建并发布网站。
