# CUDA 并行编程完全指南

本项目只包含 CUDA 交互式电子书，使用 MkDocs Material 构建和发布。电子书本身是独立 HTML，章节及图片资源位于 `docs/cuda-ebook/`。

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

## 发布到 GitHub Pages

`.github/workflows/deploy.yml` 会在推送到 `main` 分支后自动构建并发布。请在 GitHub 仓库的 **Settings → Pages → Build and deployment → Source** 中选择 **GitHub Actions**。
