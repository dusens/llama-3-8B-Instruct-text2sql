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
| **llama-3-8B-Instruct-text2sql-lora**<br/> | [[🤗Hugging Face]](https://huggingface.co/dusensen/llama-3-8B-Instruct-text2sql-lora)<br/> [[🤖ModelScope]](https://www.modelscope.cn/models/senjia/llama-3-8B-Instruct-text2sql-lora/files)<br/>|

- 本项目微调用到的数据集
- [Spider](https://yale-lily.github.io/spider): 一个跨域的复杂text2sql数据集，包含了10,181条自然语言问句、分布在200个独立数据库中的5,693条SQL，内容覆盖了138个不同的领域。
- [CHASE](https://xjtu-intsoft.github.io/chase/): 一个跨领域多轮交互text2sql中文数据集，包含5459个多轮问题组成的列表，一共17940个<query, SQL>二元组，涉及280个不同领域的数据库。
- [BIRD-SQL：](https://bird-bench.github.io/)数据集是一个英文的大规模跨领域文本到SQL基准测试，特别关注大型数据库内容。该数据集包含12,751对文本到SQL数据对和95个数据库，总大小为33.4GB，跨越37个职业领域。BIRD-SQL数据集通过探索三个额外的挑战，即处理大规模和混乱的数据库值、外部知识推理和优化SQL执行效率，缩小了文本到SQL研究与实际应用之间的差距。
- [CSpider：](https://drive.google.com/drive/folders/1TxCUq1ydPuBdDdHF3MkHT-8zixluQuLa?usp=sharing)2019年9月，西湖大学提出了一个大型中文数据集CSpider，用于复杂和跨领域的语义解析和Text-to-SQL任务，由2位NLP研究人员和1位计算机专业学生从数据集Spider翻译而来，其中包含200个数据库上的10181个问题和5693个独特的复杂SQL查询，具有涵盖138个不同领域的多个表的数据库。


## 贡献者

## 许可证
本项目采用 MIT 许可证。详细许可信息可以在项目仓库的LICENSE文件中找到。

## 如何参与
欢迎对中文处理和SQL生成感兴趣的开发者加入我们的项目。你可以通过 GitHub Issue 或 Pull Request 的方式参与项目贡献。

