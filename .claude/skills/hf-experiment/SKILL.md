---
name: hf-experiment
description: 为给定的 HuggingFace pipeline 任务（如 text-classification、translation_en_to_fr）创建实验脚本，并将结论追加到 learning_log.md。
---

在 code_to_learn/ 目录下创建新的 Python 实验文件，使用 transformers pipeline API，提供有代表性的示例输入。说明将加载的默认模型、输出格式，并将简要实验结论追加到项目根目录的 learning_log.md（不存在则创建）。
