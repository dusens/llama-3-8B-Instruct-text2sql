# 项目名称：llama-3-8B-Instruct-text2sql

## 项目简介
本项目旨在开发和训练一个基于 LLM (Large Language Model) 的模型，该模型可以接受中文自然语言指令并转换为SQL查询语句。我们的目标是提高数据库查询语言的自动化程度，使非专业用户也能轻松进行数据查询。

## 训练数据
本项目初期使用的训练数据集为 **CSPIDER 中文数据集**，该数据集包含多种数据库环境下的中文到SQL的查询转换样本。我们计划在后续阶段引入更多样的中文文本到SQL的样本，以增强模型的泛化能力和准确性。

## 模型架构
微调模型采用的是 `Llama-3-Chinese-8B-Instruct-v2` 版本，

## 功能和特点
- **自然语言理解**：能够准确理解中文自然语言输入。
- **SQL生成**：基于理解的内容生成符合逻辑的SQL查询语句。

## 部署和使用
### 下载地址

| 模型名称                  |                    LoRA版                    |
| :------------------------ | :----------------------------------------------------------: |
| **llama-3-8B-Instruct-text2sql-lora**<br/>(指令模型) | [[🤗Hugging Face]](https://huggingface.co/dusensen/llama-3-8B-Instruct-text2sql-lora)<br/> [[🤖ModelScope]](https://huggingface.co/dusensen/llama-3-8B-Instruct-text2sql-lora)<br/>|

## 贡献者

## 许可证
本项目采用 MIT 许可证。详细许可信息可以在项目仓库的LICENSE文件中找到。

## 如何参与
欢迎对中文处理和SQL生成感兴趣的开发者加入我们的项目。你可以通过 GitHub Issue 或 Pull Request 的方式参与项目贡献。

