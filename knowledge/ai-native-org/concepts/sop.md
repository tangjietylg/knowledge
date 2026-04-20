# SOP：AI-native 游戏生产的核心抽象

## 核心定义

SOP（Standard Operating Procedure）把「人的隐性经验」压缩成「可复制执行的显性流程」。

在 AI-native 游戏生产中：

> **AI-native SOP = 实体 + Skills + Pipeline**
>
> 通过实体管理数据资产，通过 Skills 加工数据，通过 Pipeline 编排多工种协作。

---

## 游戏行业的 SOP 本质

```
剧本
    ↓ 实体抽取
角色 / 场景 / 道具 / NPC / 事件 / 规则 ...（实体）
    ↓ Skills 加工
实体规格 → 美术规格 → 程序规格
    ↓ Pipeline 编排
游戏世界
```

**实体是 SOP 的载体，Skills 是加工能力，Pipeline 是协作方式。**

---

## 三层抽象

### 实体（Structured Data）

实体 = 结构化的游戏数据资产。

每个实体包含：
- **基础元数据**：名称、类型、版本、状态
- **规格描述**：完整的上下文信息
- **关联关系**：与其他实体的连接
- **交付标准**：后续工种的产出规格

**实体是 Skills 的输入和输出，是 Pipeline 的流动单位。**

### Skills（能力的原子化单元）

Skills 是对实体的加工能力，每个 Skill 定义：
- 输入格式（什么实体）
- 输出格式（产出什么）
- 适用场景
- 边界限制

游戏行业的 Skills：
- 角色解析 Skill → 从角色实体生成美术规格
- 场景解析 Skill → 从场景实体生成关卡设计
- 美术规格 Skill → 从解析结果生成美术需求
- 程序接口 Skill → 从美术规格生成程序实现

**Skills 是 Pipeline 的构建块。**

### Pipeline（多工种协作的编排）

Pipeline 把多个 Skills 串起来：
- Skills 之间的时序和依赖
- 数据如何在 Skills 之间流转
- 异常处理和分支逻辑

```
剧本 → 实体抽取 Pipeline → 角色/场景/道具实体
                              ↓
                         美术加工 Pipeline → 美术资产
                              ↓
                         程序接入 Pipeline → 程序资产
                              ↓
                         游戏世界
```

**Pipeline 是 SOP 的执行引擎。**

---

## 为什么游戏行业最需要 AI-native SOP

游戏行业的复杂度是指数级的：
- 角色 dozens → 关系网状
- 场景 dozens → 规则嵌套
- 道具 hundreds → 系统联动

**人与人的沟通无法 scale，实体在 Pipeline 里流动才能 scale。**

---

## 与 Context Engineering 的关联

| CE 概念 | 在游戏生产 SOP 中的对应 |
|:---|:---|
| Schema 定义 | 实体 Schema（角色/场景/道具...） |
| 连接设计 | 实体之间的关系（角色-场景、道具-NPC...） |
| 输入质量 | 实体规格的完整性和一致性 |
| 三方责任 | Skills 供应商提供工具，Schema 只有自己能做 |
| 健康检查 | 实体的定期维护和一致性校验 |

---

## 先行者红利

AI-native 游戏生产一旦建立：

```
实体越多 → 每次调用的上下文越丰富 → AI 产出越精确
Pipeline 越成熟 → 多工种协作越顺畅 → 产能指数增长
实体网络 → 知识积累的时间壁垒，无法用资金复制
```

**真正的护城河是时间积累的结构化资产。**

---

## 关联概念

- **实体**：游戏数据资产的基本单位
- **Skills**：对实体的加工能力
- **Pipeline**：多工种协作的编排
- **Context Engineering**：实体结构化的理论支撑