# Context Structure：LLM 输入拆解

> 相关阅读：[[agent-modules]] — Agent 侧五大子模块详解
> 相关阅读：[[../02-core-concepts|02-core-concepts]] — 三方责任框架

## 复合结构

LLM 的输入不是单一的"问题"，而是一个**复合结构**，包含多个组成部分：

| 组成部分 | 来源 | 说明 |
|---------|------|------|
| System Prompt | Agent 定义 | 角色定义、能力边界、行为约束 |
| User Query | 用户 | 即时请求，通常很短 |
| Conversation History | Agent 维护 | 多轮对话上下文 |
| Retrieved Context | RAG 召回 | 从外部知识库召回的内容 |
| Tool Outputs | Agent 调用 | 搜索、代码执行等工具结果 |
| User-provided Artifacts | 用户 | 上传的文件、表格、结构化数据 |

## 关键洞察

**用户 Query 通常很短，但真正的信息量在 Retrieved Context。**

Retrieved Context 的质量直接决定 LLM 的输出质量。而它的质量取决于：
- 召回策略是否精准
- 知识库是否结构化
- 数据治理是否到位

## 大多数人的误区

看到 Context Engineering 这个词，默认以为它是 **Agent 这侧的事情**。

但实际上，**Retrieved Context 的质量取决于企业和个人自己做的数据治理**。

Schema 设计得合理，召回的东西才精准；知识分层做得好，上下文才不会被无关信息稀释。

## 为什么这个拆解重要

把输入结构打开看，逐字段分析，比套任何大词（harness、agents）都更接近本质。

- Harness/Agents 是 WHAT —— 定义边界
- Context Engineering 是 HOW —— 怎么组织输入

## Input 类型是开放的，不是封闭的

上面列出的 6 种 Input 类型（System Prompt / User Query / Conversation History / Retrieved Context / Tool Outputs / User-provided Artifacts）不是终态，只是**到目前为止被显性化了的**。

随着模型能力边界的扩展、工具类型的增加，Input 的类型还会继续扩充——比如某种新的"实时上下文"类型，或者模型原生输出的某种中间状态反过来作为另一轮的输入（Checkpoint / Resume 之类）。

Context Engineering 的框架价值在于：它不限制你只能有这几种，而是告诉你**"拆解 Input 这件事本身"是值得持续做的**——每拆出一种新类型，就意味着有一个以前被忽视的输入质量瓶颈被抓住了。

## 最底层范式

```
Input + Model = Output
```

Harness 没有跳出这个范式，它只是在 **System Prompt + Tools Integration** 这两层里做文章——定义 AI 能做什么、行为边界是什么、调用哪些工具。技术供应商负责 Agent 侧模块（System Prompt、Tool Outputs）的标准化，而 **Retrieved Context 的质量永远需要自己负责**。

## 祛魅：追概念不如掌握底层

行业每隔几个月就出一个"颠覆性"新概念——prompt engineering → context engineering → agentic AI → harness——看似层层颠覆，实际上**每次都是在 Input 侧换一个更精确的词来描述同一件事**。

模型在变、工具在变、buzzword 在变，但 `Input + Model = Output` 这个等式从来没变过。

掌握底层框架的人永远淡定，因为任何新概念出来都能往这个框架里装。追概念的人永远在被淘汰，因为下一个马上就要来。

## Prompt Builder 的本质：可扩展的列表 + injection

Prompt Builder 的架构实现，本质上是一个**有序列表**——每次往里 inject 一段 context，列表扩大，上下文变厚，输出质量提升。

核心价值是**可扩展性**：你不知道用户在哪个时刻需要什么补充信息，所以这套系统必须是开放的、插件式的。今天挂一个知识库召回，明天挂一个实时搜索结果，后天挂一个用户上传的文档——本质都是往列表里追加条目，与"Input 类型是开放的"这一思想一脉相承。

## 关联

- [[../02-core-concepts|02-core-concepts]] — 三方责任框架的完整推导
- [[agent-modules]] — Agent 侧子模块（Retriever 连接 CE 与数据治理）
