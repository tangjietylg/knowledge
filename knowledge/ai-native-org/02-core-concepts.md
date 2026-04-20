# AI-native 组织理论：核心概念

## 核心命题

> **AI 能力的组织化，由知识网络的连接质量决定。**

这个命题与 Context Engineering 一脉相承：
- CE 解决的是 AI 输入质量问题
- AI-native 组织解决的是 AI 能力如何通过网络产生乘积效应

---

## 核心洞察

**Structured Data + Skills + Pipeline = AI-native SOP**

这是 AI 时代的 SOP 形式，是让 AI 能力成为组织资产的核心抽象。

---

## 三层抽象

### 1. Structured Data（输入输出的结构化）

**对应传统 SOP 中的：** 输入 + 输出 + 判断条件

Structured Data 是 AI-native SOP 的根基——没有结构化，Pipeline 无法知道上一级的输出如何匹配下一级的输入。

```
CE 视角：
- Input 的每个组成部分都是 Structured Data
- Retrieved Context 的质量取决于结构化程度
- Schema 定义决定 Structured Data 的字段和类型

AI-native SOP 视角：
- Skills 的输入格式：Structured Data
- Skills 的输出格式：Structured Data
- Pipeline 的条件分支：Structured Data 的判断
```

### 2. Skills（能力的原子化单元）

**对应传统 SOP 中的：** 角色 + 工具

每个 Skill 是一个完整的 mini SOP：

| 要素 | 说明 |
|:---|:---|
| 输入格式 | 明确的 Structured Data 格式 |
| 输出格式 | 明确的 Structured Data 格式 |
| 适用场景 | 什么情况下调用这个 Skill |
| 边界限制 | 什么情况下不该用这个 Skill |

Skills 是 Pipeline 的构建块，也是 Context Engineering 在 Skill 设计领域的延伸。

**Skill Design Principles**（见 `concepts/skill-design-principles.md`）就是 Skills 的设计原则。

### 3. Pipeline（能力的编排和连接）

**对应传统 SOP 中的：** 步骤 + 时序关系

Pipeline 把多个 Skills 连起来：

```
Skills 之间的时序和依赖
数据如何在 Skills 之间流转
异常处理和分支逻辑
条件分支的判断规则
```

Pipeline 是 SOP 在 AI-native 时代的执行引擎。

---

## 与传统 SOP 的对比

| 维度 | 传统 SOP | AI-native SOP |
|:---|:---|:---|
| **执行者** | 人 | AI |
| **结构化对象** | 人的经验 | AI 能力的调用方式 |
| **核心抽象** | 步骤 + 角色 + 工具 + 判断 | Structured Data + Skills + Pipeline |
| **产出形式** | 文档/流程图 | 可执行的知识网络 |
| **维护方式** | 人工更新 | 人机协同 |
| **扩展性** | 受限于人的理解成本 | 节点越多，连接价值越大 |
| **解决的核心问题** | 经验传承 | 连接建立 |

---

## SOP 是 AI-native 组织转型的最佳切入点

已有的 SOP 体系就是最好的起点：

1. **SOP 本身已经是结构化的知识资产** — 经验已经被压缩成显性流程
2. **SOP 有明确的使用场景和执行边界** — 升级成本低、风险低
3. **SOP 的结构化维度与 AI-native 三层抽象天然对应**

升级 SOP 的结构化程度，不需要从零开始，只需要把已有的 SOP 用 Structured Data + Skills + Pipeline 重新表达。

---

## 先行者红利

AI-native SOP 一旦建立并与知识网络打通：

```
节点越多 → 每次调用的上下文越丰富 → 能力越强
连接越密 → Skills 之间的协作越顺畅 → 效率越高
维护成本 → 随自动化程度下降
积累价值 → 指数增长
```

**时间积累的优势是资金无法快速购买的。SOP 的成熟度就是证明。**

---

## 关联概念

- **SOP**：AI-native 组织的能力载体（详见 `concepts/sop.md`）
- **Skill Design Principles**：Skills 的设计原则（详见 `context-engineering/concepts/skill-design-principles.md`）
- **Structured Data**：SOP 的输入输出结构化形式
- **Pipeline**：Skills 的编排逻辑，SOP 的执行引擎