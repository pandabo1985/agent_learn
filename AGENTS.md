# 仓库指南

## 项目结构与模块组织

本仓库是一个小型 AI 学习工作区。根目录下的 `*.html` 文件是独立的教学页面和演示，CSS 与 JavaScript 均内联在页面中。根目录的 Markdown 设计规范记录了这些学习页面的视觉语言。`code_to_learn/` 存放 Python 示例：`main.py` 是一个最小脚本，`pipeline_test.py` 演示 Hugging Face `transformers` 的情感分析 pipeline。目前没有专用的 `tests/`、`assets/`、包清单或构建输出目录。

## 构建、测试与开发命令

- `python3 code_to_learn/main.py`：运行简单的 Python 冒烟示例。
- `python3 code_to_learn/pipeline_test.py`：运行 Transformers pipeline 演示；需要安装 `transformers`，并可能下载模型文件。
- `python3 -m http.server 8000`：从仓库根目录本地托管静态 HTML 页面。
- `open http://localhost:8000/hf_llm_course_chapter1.html`：在 macOS 上预览已托管的页面。

当前没有正式构建步骤。如果后续添加依赖，优先使用固定版本的 `requirements.txt` 或 `pyproject.toml`，并在此处记录安装命令。

## 代码风格与命名约定

Python 使用 4 空格缩进，并保持脚本可作为直接示例运行。函数名优先使用清晰、描述性的 `snake_case`。HTML 演示应保持自包含，除非确实需要共享资源。遵循现有静态页面风格：语义化分区、在 `:root` 中定义 CSS 自定义属性，并在中文页面中保持易读的中文教学文案。不要提交生成缓存、下载的模型权重或虚拟环境。

生成或修改 HTML 页面时，必须参考 `设计规范.md`，沿用其中的配色变量、布局结构、组件模式和交互规范。若确需偏离规范，应在变更说明中写明原因，并提供浏览器预览或截图验证。

## 测试指南

目前尚未配置测试框架。对于 Python 变更，当代码从纯演示变为可复用行为时，应在 `tests/` 下添加聚焦的 `pytest` 测试。测试文件命名为 `test_*.py`，并使用 `python3 -m pytest` 运行。对于 HTML 变更，应在浏览器中手动预览受影响页面，检查导航、响应式布局和控制台错误。

## 提交与 Pull Request 指南

当前检出目录不包含 `.git/`，因此无法从本地提交历史推断约定。提交信息应简短并使用祈使句，例如 `Add transformer attention demo` 或 `Fix pipeline example import`。Pull Request 应说明修改了哪个学习页面或脚本，列出手动验证步骤；涉及 HTML 视觉变更时应附截图。

## 安全与配置提示

不要把密钥写入源码文件。Hugging Face 示例应通过环境变量读取 token，不要提交下载的模型缓存。
