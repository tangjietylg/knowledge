# Context Engineering

## 概念全景

Context Engineering 是解决"AI 输入质量"问题的实践体系。

核心命题：**大模型输出的质量，由输入的上下文质量决定。** 而输入质量的核心不在于模型，在于数据治理。

## 核心观点

1. **结构化是前提，不是结果**  
   代码天然结构化，所以 AI 在编程领域效果拔群；剧本、小说、业务文档天然非结构化，不做治理就无法规模化应用。

2. **三方责任框架**（关键论证）  
   从输入拆解看，Context Engineering 分三方：Agent 侧（技术供应商负责）、LLM 侧（大厂负责）、知识库侧（企业/个人自己负责）。前两者会越来越标准化，但知识库侧没有标准答案，必须自己做。

3. **Context Engineering ≠ Harness/Agents**  
   - Harness/Agents 是 WHAT——定义边界、流程、工具  
   - Context Engineering 是 HOW——怎么组织输入、怎么治理数据、怎么让上下文在正确时间出现正确内容  
   两者解决不同层次的问题，是两条并行的线。

4. **检索与理解必须分离**  
   RAG 的局限：它解决的是"用时现搜"，但真正的理解需要"提前结构化"。离线完成理解与结构化，在线只做查询和推理。

5. **输入质量决定输出质量**  
   AI 写长剧本时，要像"一个真正了解这个世界的人"，必须保证信息的完整性和一致性。这无法靠 RAG 达成，必须靠原材料的结构化。

6. **Agent 侧子模块**  
   Agent 包含五大模块（Prompt Builder / Context Engine / Memory Manager / Retriever / Tool Integrator），它们解决的是"怎么组织输入"，但输入原材料本身的质量仍然是数据治理侧的责任。

## 知识体系结构

```
context-engineering/
├── 01-problem-analysis.md    # 问题分析：RAG 的根本局限
├── 02-core-concepts.md       # 核心概念澄清（含三方责任框架）
├── 03-practices.md           # 实践方法
├── 04-case-studies.md        # 案例
├── 05-conclusion.md          # 结论：为什么 Context Engineering 最重要
└── concepts/                 # 子概念原子化
    ├── llm-wiki.md           # LLM-Wiki 框架
    ├── rag-limitations.md    # RAG 的局限
    ├── code-vs-script.md     # 代码与剧本的对比
    ├── context-structure.md  # 输入结构拆解
    ├── data-governance.md    # 数据治理
    └── agent-modules.md      # Agent 侧子模块拆解
```

## 关联概念

- **LLM-Wiki**：领域知识库的结构化框架
- **Context Structure**：LLM 输入的组成拆解
- **Data Governance**：企业和个人必须自己做的数据治理工作
- **RAG Limitations**：为什么"现搜"不够，必须"预结构化"
- **Agent Modules**：Agent 侧五大子模块（Prompt Builder / Context Engine / Memory Manager / Retriever / Tool Integrator）

---

> 核心精神：**技术会标准化，但数据不会。越早做结构化，收益越大。**
