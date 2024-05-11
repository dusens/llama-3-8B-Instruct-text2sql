# 项目名称：llama-3-8B-Instruct-text2sql

## 项目简介
本项目旨在开发和训练一个基于 llama-3-8B-Instruct 的模型，该模型可以接受中文自然语言指令并转换为SQL查询语句。

## 训练数据
  本项目初期使用的训练数据集为 **CSPIDER 中文数据集 Spider数据集 BIRD-SQL 数据集**，该数据集包含多种数据库环境下的中文到SQL的查询转换样本。
  我们计划在后续阶段引入更多样的中文文本到SQL的样本，以增强模型的泛化能力和准确性。   
  
- [Spider](https://yale-lily.github.io/spider): 一个跨域的复杂text2sql数据集，包含了10,181条自然语言问句、分布在200个独立数据库中的5,693条SQL，内容覆盖了138个不同的领域。
- [BIRD-SQL：](https://bird-bench.github.io/)数据集是一个英文的大规模跨领域文本到SQL基准测试，特别关注大型数据库内容。该数据集包含12,751对文本到SQL数据对和95个数据库，总大小为33.4GB，跨越37个职业领域。BIRD-SQL数据集通过探索三个额外的挑战，即处理大规模和混乱的数据库值、外部知识推理和优化SQL执行效率，缩小了文本到SQL研究与实际应用之间的差距。
- [CSpider：](https://drive.google.com/drive/folders/1TxCUq1ydPuBdDdHF3MkHT-8zixluQuLa?usp=sharing)2019年9月，西湖大学提出了一个大型中文数据集CSpider，用于复杂和跨领域的语义解析和Text-to-SQL任务，由2位NLP研究人员和1位计算机专业学生从数据集Spider翻译而来，其中包含200个数据库上的10181个问题和5693个独特的复杂SQL查询，具有涵盖138个不同领域的多个表的数据库。

## 模型架构
微调模型采用的是 `Llama-3-Chinese-8B-Instruct-v2` 版本，

## 功能和特点
- **自然语言理解**：能够准确理解中文自然语言输入。
- **SQL生成**：基于理解的内容生成符合逻辑的SQL查询语句。

<Gallery />



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
    <td>Llama2-7B-Chat</td>
    <td>lora</td>
    <td>0.887</td>
    <td>0.641</td>
    <td>0.489</td>
    <td>0.331</td>
    <td>0.626</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0.847</td>
    <td>0.623</td>
    <td>0.466</td>
    <td>0.361</td>
    <td>0.608</td>
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
  <td>CodeLlama-7B-Instruct</td>
    <td>lora</td>
    <td>0.923</td>
    <td>0.756</td>
    <td>0.586</td>
    <td>0.349</td>
    <td>0.702</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0.911</td>
    <td>0.751</td>
    <td>0.598</td>
    <td>0.331</td>
    <td>0.696</td>
  </tr>
  <tr>
    <td></td>
    <td>base</td>
    <td>0.698</td>
    <td>0.601</td>
    <td>0.408</td>
    <td>0.271</td>
    <td>0.539</td>
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
    <td>Baichuan2-7B-Chat</td>
    <td>lora</td>
    <td>0.871</td>
    <td>0.63</td>
    <td>0.448</td>
    <td>0.295</td>
    <td>0.603</td>
  </tr>
  <tr>
  <td></td>
    <td>qlora</td>
    <td>0.891</td>
    <td>0.637</td>
    <td>0.489</td>
    <td>0.331</td>
    <td>0.624</td>
  </tr>
  <tr>
    <td></td>
    <td>base</td>
    <td>0.581</td>
    <td>0.413</td>
    <td>0.264</td>
    <td>0.187</td>
    <td>0.392</td>
  </tr>
    <tr>
    <td>Baichuan2-13B-Chat</td>
    <td>lora</td>
    <td>0.903</td>
    <td>0.702</td>
    <td>0.569</td>
    <td>0.392</td>
    <td>0.678</td>
    </tr>
  <tr>
  <td></td>
    <td>qlora</td>
    <td>0.895</td>
    <td>0.675</td>
    <td>0.58</td>
    <td>0.343</td>
    <td>0.659</td>
  </tr>
  <tr>
  <td></td>
  <td>base</td>
  <td>0.395</td>
  <td>0.256</td>
  <td>0.138</td>
  <td>0.042</td>
  <td>0.235</td>
  </tr>
<tr>
<td>Qwen-7B-Chat</td>
  <td>lora</td>
  <td>0.855</td>
  <td>0.688</td>
  <td>0.575</td>
  <td>0.331</td>
  <td>0.652</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0.911</td>
    <td>0.675</td>
    <td>0.575</td>
    <td>0.343</td>
    <td>0.662</td>
  </tr>
  <tr>
  <td></td>
  <td>base</td>
  <td>0.871</td>
  <td>0.632</td>
  <td>0.368</td>
  <td>0.181</td>
  <td>0.573</td>
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
  <tr>
    <td>ChatGLM3-6b</td>
    <td>lora</td>
    <td>0.855</td>
    <td>0.605</td>
    <td>0.477</td>
    <td>0.271</td>
    <td>0.59</td>
  </tr>
  <tr>
    <td></td>
    <td>qlora</td>
    <td>0.843</td>
    <td>0.603</td>
    <td>0.506</td>
    <td>0.211</td>
    <td>0.581</td>
  </tr>
</table>

## 下载地址

| 模型名称                  |                    完整版                    |                    LoRA版                    |                    GGUF版                    |
| :------------------------ | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| **llama-3-8B-Instruct-text2sql**<br/>(指令模型) | [[🤗Hugging Face]]()<br/> [[🤖ModelScope]](https://www.modelscope.cn/models/senjia/llama-3-8B-Instruct-text2sql/summary)<br/>[[wisemodel]]() | [[🤗Hugging Face]]()<br/> [[🤖ModelScope]](https://www.modelscope.cn/models/senjia/llama-3-8B-Instruct-text2sql-lora/summary)<br/>[[wisemodel]]() |  |


## 贡献者
sensen
## 许可证
本项目采用 MIT 许可证。详细许可信息可以在项目仓库的LICENSE文件中找到。

## 如何参与
欢迎对中文处理和SQL生成感兴趣的开发者加入我们的项目。你可以通过 GitHub Issue 或 Pull Request 的方式参与项目贡献。

