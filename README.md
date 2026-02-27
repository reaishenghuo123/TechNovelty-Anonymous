# TechNovelty-Bench: Evaluation Dataset for Technology Novelty Search

⚠️ **Anonymous Repository for Double-Blind Review / 双盲评审专用匿名仓库** ⚠️

Welcome to the official anonymous repository for the paper: **"TNC-Agent: Research on Human-AI Collaborative Intelligence Agent and Comparative Reasoning Framework for Technology Novelty Search"**. 
欢迎访问本文的官方匿名双盲评审仓库。

---

## 1. Introduction (简介)
**TechNovelty-Bench** is a vertical-domain evaluation benchmark designed for High-intensity Logical Stress Testing of Large Language Models (LLMs) and Agents in the field of Technology Novelty Search. Unlike traditional retrieval benchmarks, it focuses on evaluating models' capabilities in **fine-grained parameter-level differential reasoning** when dealing with highly homogeneous academic and patent texts.

**TechNovelty-Bench** 是一个垂直领域的评测基准，专为科技查新场景下大语言模型与智能体的高强度逻辑压力测试而设计。与传统检索评测不同，它侧重于评估模型在面对高度同质化学术与专利文本时，进行**细粒度、参数级差分推理**的能力。

---

## 2. Data Availability & NDA Statement (数据可用性与保密声明)
The original dataset consists of 500 real-world novelty search queries and corresponding evidence documents sourced from a provincial science and technology information institute. 

🔒 **Privacy & NDA:** Due to Non-Disclosure Agreements (NDAs) regarding commercial core technologies and intellectual property protection, the full 500-pair dataset cannot be fully open-sourced at this stage. 

To support academic reproducibility, we have rigorously desensitized (entity anonymization) and extracted **50 highly representative samples** to form the `sample_dataset.csv`. The full dataset will be partially released upon the formal acceptance of the paper under strict privacy constraints.

原始评测数据集包含 500 对来自某省情报所的真实查新委托及支撑文献。
🔒 **保密声明**：受限于合作机构的保密协议（NDA）及核心技术产权保护要求，完整的 500 对数据集现阶段无法全量开源。为了最大程度支持学术复现，我们经过严格的实体脱敏处理，抽样提取了 **50 对极具代表性的查新样本**（详见 `sample_dataset.csv`）。完整数据集将在论文正式录用后，在合法合规的前提下进一步开源。

---

## 3. Dataset Structure (数据结构说明)
The provided `sample_dataset.csv` covers three major domains: Electronic Information (电子信息), Mechanical Manufacturing (机械制造), and Biomedicine (生物医药). 

Data fields are structured as follows (数据字段说明):

| Column Name (列名) | Description (说明) |
| :--- | :--- |
| `样本编号 (ID)` | Unique identifier for each sample / 样本唯一标识符 |
| `所属领域 (Domain)` | Technological domain (Electronics, Mechanics, BioMed) / 所属技术领域 |
| `查新点核心技术特征 (Query)` | The core technical features claimed to be novel / 待查新的核心技术特征 |
| `对比文献关键片段 (Evidence)` | The retrieved highly relevant literature snippet / 检索召回的密切相关文献片段 |
| `专家标注 (Label)` | Human expert evaluation: 新颖(Novel/Disjoint), 部分新颖(Partially Novel/Intersecting), 不新颖(Not Novel/Inclusive) / 资深查新员给出的金标准判决 |
| `细粒度差异说明 (Rationale)` | The logical reasoning process explaining the label / 解释该判决逻辑的差分特征说明 |

---

## 4. Evaluation Paradigm (评测范式)
This dataset is intended to evaluate the reasoning logic of LLMs. In our paper, we evaluated:
1. **Zero-shot LLM** (e.g., GPT-4, DeepSeek-V3, DeepSeek-R1)
2. **Standard RAG** (Naive retrieval-augmented generation)
3. **TNC-Agent (Ours)** (Equipped with Semantic Circuit Breaker & Comp-CoT)

Researchers can use the `Query` and `Evidence` columns as prompts to test whether their models can accurately deduce the `Label` through proper logical reasoning.

研究者可提取 `Query` 与 `Evidence` 列作为输入，测试各类大模型与智能体框架是否能准确推导出对应的 `Label` 结论。
