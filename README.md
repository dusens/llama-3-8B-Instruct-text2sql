# 项目名称：llama-3-8B-Instruct-text2sql

## 项目简介
该模型可以接受中文自然语言指令并转换为SQL查询语句。

## 新闻

**[2024/07/18]  发布 llama-3-8B-sqlcorder-chinese-Instruct-gguf ，对中文对话能力进行微调,进行了中文text2sql的微调：[hungingface 地址](https://huggingface.co/text2sql/llama-3-8B-sqlcorder-chinese-Instruct-gguf)**

## 接下来方向
- 放出 LLaMA-Factory 微调教程
- 如何使用测试集进行测试
## 模型指标
- 更新日期: 2024/05/11
- 评价指标: execution accuracy (ex)

<table style="text-align: center;">
  <tr>
    <th style="text-align: center;">Model</th>
    <th>Method</th>
    <th>Easy</th>
    <th>Medium</th>
    <th>Hard</th>
    <th>Extra</th>
    <th>All</th>
  </tr>
    <tr>
    <td>llama-3-8B-Instruct-text2sql</td>
    <td>lora</td>
    <td>0.938</td>
    <td>0.782</td>
    <td>0.581</td>
    <td>0.524</td>
    <td>0.768</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td></td>
    <td>base</td>
    <td>0.297</td>
    <td>0.245</td>
    <td>0.151</td>
    <td>0.095</td>
    <td>0.230</td>
  </tr>
  <tr>
    <td></td>
    <td>base</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Llama2-13B-Chat</td>
    <td>lora</td>
    <td>0.907</td>
    <td>0.729</td>
    <td>0.552</td>
    <td>0.343</td>
    <td>0.68</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0.911</td>
    <td>0.7</td>
    <td>0.552</td>
    <td>0.319</td>
    <td>0.664</td>
  </tr>
  <tr>
    <td></td>
    <td>base</td>
    <td>0.214</td>
    <td>0.177</td>
    <td>0.092</td>
    <td>0.036</td>
    <td>0.149</td>
  </tr>
  <tr>
    <td>CodeLlama-13B-Instruct</td>
    <td>lora</td>
    <td>0.94</td>
    <td>0.789</td>
    <td>0.684</td>
    <td>0.404</td>
    <td>0.746</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0.94</td>
    <td>0.774</td>
    <td>0.626</td>
    <td>0.392</td>
    <td>0.727</td>
  </tr>
  <tr>
    <td></td>
    <td>base</td>
    <td>0.577</td>
    <td>0.352</td>
    <td>0.201</td>
    <td>0.066</td>
    <td>0.335</td>
  </tr>
  <tr>
    <td>Qwen-14B-Chat</td>
    <td>lora</td>
    <td>0.895</td>
    <td>0.702</td>
    <td>0.552</td>
    <td>0.331</td>
    <td>0.663</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0.919</td>
    <td>0.744</td>
    <td>0.598</td>
    <td>0.367</td>
  <td>0.701</td>
  </tr>
    <tr>
    <td></td>
    <td>base</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
  </tr>
</table>

## 训练数据
  本项目初期使用的训练数据集为 **CSPIDER 中文数据集 Spider数据集 BIRD-SQL 数据集**，该数据集包含多种数据库环境下的中文到SQL的查询转换样本。
  我们计划在后续阶段引入更多样的中文文本到SQL的样本，以增强模型的泛化能力和准确性。   
  
- [Spider](https://yale-lily.github.io/spider): 一个跨域的复杂text2sql数据集，包含了10,181条自然语言问句、分布在200个独立数据库中的5,693条SQL，内容覆盖了138个不同的领域。
- [BIRD-SQL：](https://bird-bench.github.io/)数据集是一个英文的大规模跨领域文本到SQL基准测试，特别关注大型数据库内容。该数据集包含12,751对文本到SQL数据对和95个数据库，总大小为33.4GB，跨越37个职业领域。BIRD-SQL数据集通过探索三个额外的挑战，即处理大规模和混乱的数据库值、外部知识推理和优化SQL执行效率，缩小了文本到SQL研究与实际应用之间的差距。
- [CSpider：](https://drive.google.com/drive/folders/1TxCUq1ydPuBdDdHF3MkHT-8zixluQuLa?usp=sharing)2019年9月，西湖大学提出了一个大型中文数据集CSpider，用于复杂和跨领域的语义解析和Text-to-SQL任务，由2位NLP研究人员和1位计算机专业学生从数据集Spider翻译而来，其中包含200个数据库上的10181个问题和5693个独特的复杂SQL查询，具有涵盖138个不同领域的多个表的数据库。
- [WikiSQL：](https://github.com/salesforce/WikiSQL)2017/09，Salesforce提出了一个大型Text-to-SQL数据集WikiSQL，数据来自Wikipedia，属于单个域，包含80,654个自然语言问题和77,840条SQL语句。 SQL语句的形式比较简单，不包含排序、分组、子查询等复杂操作。
- [SParC ：](https://drive.usercontent.google.com/download?id=1Uu7NMHTR1tdQw1t7bAuM7OPU4LElVKfg&export=download&authuser=0)2019/06，耶鲁大学提出了一个大型数据集 SParC，用于复杂、跨域、上下文相关（多轮）语义解析和文本到 SQL 任务，该数据集由 4,298 个连贯的问题序列组成（12k+ 个带注释的独特个人问题）由 14 名耶鲁大学学生注释的 SQL 查询），从用户与 138 个领域的 200 个复杂数据库的交互中获得。

## 下载地址

| 模型名称                  |                    完整版                    |                    LoRA版                    |                    GGUF版                    |
| :------------------------ | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| **llama-3-8B-Instruct-text2sql**<br/>(基于Llama-3-Chinese-8B-Instruct-v2) | [[🤗Hugging Face]]()<br/> [[🤖ModelScope]](https://www.modelscope.cn/models/senjia/llama-3-8B-Instruct-text2sql/summary)<br/>[[wisemodel]]() | [[🤗Hugging Face]]()<br/> [[🤖ModelScope]](https://www.modelscope.cn/models/senjia/llama-3-8B-Instruct-text2sql-lora/summary)<br/>[[wisemodel]]() |  |
| **llama-3-8B-sqlcorder-chinese-Instruct-gguf**<br/>(基于llama-3-8b-sqlcorder) | |  |[[🤗Hugging Face]](https://huggingface.co/text2sql/llama-3-8B-sqlcorder-chinese-Instruct-gguf)<br/>|

## 贡献者
sensen
## 许可证
本项目采用 MIT 许可证。详细许可信息可以在项目仓库的LICENSE文件中找到。

## 如何参与
欢迎对中文处理和SQL生成感兴趣的开发者加入我们的项目。你可以通过 GitHub Issue 或 Pull Request 的方式参与项目贡献。

