# AI Agent 创业机会：从 Vertical Workflow 到 Persistent Intelligence

**讨论日期：2026-08-15**

> 这份文档记录一轮关于 AI Agent 创业机会的研究讨论。重点不是罗列“哪些行业适合 Agent”，而是研究：**在 Foundation Model、Agent Runtime 和通用 Workflow 平台逐渐成熟之后，一个新的 Agent 公司究竟凭什么存在，以及什么东西能够形成长期壁垒。**

---

## 1. 先抛弃“行业列表”思维

一个很容易掉进的分析陷阱是不断罗列：

- Procurement / Supply Chain
- Construction
- Insurance
- Healthcare
- Legal
- Manufacturing
- Cybersecurity
- Scientific Research

然后说“这些行业都有 Agent 机会”。

这当然没有错，但创业价值很有限。

因为其中大量所谓 Vertical Agent，本质上只是：

```text
通用 Agent Platform
        +
行业 Workflow
        +
行业 UI
        +
若干垂直 integrations / features
```

这类产品当然可以赚钱，但未必形成独立、长期的技术壁垒。一个成熟的通用 Agent / Workflow 平台完全可能快速提供行业模板，然后由客户自己配置。

因此，真正的问题不是：

> **哪个行业可以使用 Agent？**

而是：

> **为什么客户一定要选择这家 Agent 公司，而不是直接用通用 Agent 平台 + 一个模板？**

---

## 2. Vertical Agent 的几种不同类型

可以把所谓 Vertical Agent 粗略拆成几层：

```text
Vertical Agent
      │
      ├── Vertical UI
      │
      ├── Vertical Workflow
      │
      ├── Vertical Intelligence
      │
      ├── Vertical World Model
      │
      └── Agent Network / Community
```

它们的创业价值并不相同。

### 2.1 Vertical UI

专门为某个行业做一套 Agent UI。

UX 可以成为产品优势，但如果底层没有更深的资产，容易被平台复制。

### 2.2 Vertical Workflow

例如：

```text
Insurance underwriting
Procurement
Construction PM
Tax / Audit
```

如果核心价值主要是：

```text
email
→ extraction
→ rules
→ system calls
→ approval
→ output
```

那么它更接近 workflow package，而不是新的 Agent category。

这类机会存在，但对缺少深厚行业经验的创业团队并不天然友好，也不意味着可以形成长期 moat。

### 2.3 Vertical Intelligence

更值得关注的是：Agent 本身开始拥有某个行业真正重要的 **decision intelligence**。

例如不是“帮保险公司走 underwriting 流程”，而是：

> **成为真正的 underwriting intelligence。**

这需要长期积累：

```text
Domain data
+ historical outcomes
+ domain rules
+ company preferences
+ external signals
+ decision history
        ↓
Domain judgment
```

这时产品出售的不再只是 workflow，而是**判断能力本身**。

### 2.4 Vertical World Model

再往前一步，Agent 不只是做判断，而是长期维护它所负责对象的状态。

例如一个 Construction Agent 不应该只是：

> 读取合同 → 生成 RFI。

真正有价值的是：

```text
Project World Model

Schedule
Budget
Design
Contract
Material
People
Suppliers
Issues
Risk
Changes
```

Agent 持续从：

```text
Drawings
Emails
Meetings
Photos
RFI
Contracts
Invoices
Inspection
Telemetry
Schedule
```

更新这个 world model，并基于状态做长期决策。

此时 Agent 更接近一个**持续存在的数字实体**，而不是 workflow executor。

---

## 3. Agent 创业真正重要的一个方向：交付 Intelligence

我们进一步讨论了一个更本质的观点：

> **Agent 创业的核心价值，可能不是交付一个“软件功能”，而是把 LLM 的 intelligence 放进一个长期存在的实体中。**

即：

```text
Agent
=
Intelligence embedded in a persistent entity
```

一个真正有价值的 Agent 应该逐渐形成：

```text
Identity
World Model
Values
Memory
Responsibilities
Goals
Capabilities
Relationships
Judgment
Agency
```

于是用户购买的不只是：

- UI
- workflow
- chatbot
- model access

而是：

> **一个能够长期替用户承担某种判断与责任的 intelligence。**

---

## 4. Agent 的演进：Human-driven → Goal-driven → Responsibility-driven → Role-driven

这是理解下一代 Agent 产品形态的重要框架。

### Human-driven

```text
Human: 去查一下 Apple 翻新机
Agent: 执行一次任务
```

Agent 是工具。

### Goal-driven

```text
Human: 帮我找到一台合适的 M5 Max
Agent: 自己规划并完成目标
```

Agent 开始自主规划，但目标仍由人给出。

### Responsibility-driven

```text
Human: 你负责帮我长期盯住 Apple 翻新市场
```

Agent 开始承担一个持续 responsibility：

```text
Observe
→ Decide
→ Act
→ Monitor
→ Report
```

### Role-driven

```text
你是我的采购经理。
你是我的研究员。
你是这个项目的 CTO。
你是我的制片人。
```

这时，人不再需要不断提供具体 goal。

**Role 本身开始成为 goal generator。**

例如一个采购经理自然知道自己长期关心：

```text
控制成本
保证供应
降低风险
维护供应商关系
遵守公司政策
```

因此：

> **Role-driven Agent 可能比 Goal-driven Agent 更接近真正的“数字员工”。**

这也意味着长期 Agent 的核心对象不是一条 prompt，而是一整套：

```text
Role
Identity
Values / Responsibility
World Model
State
Goals
Actions
Lifecycle
```

---

## 5. 为什么纯 Vertical Workflow 容易被平台化

随着通用 Agent / Workflow 平台成熟：

```text
General Agent Runtime
        +
MCP / tools
        +
Workflow builder
        +
Template
        +
Enterprise integrations
```

很多行业 Agent 都可能被快速 productize 为模板。

因此一个 startup 如果只是：

> “我们做 Procurement Agent。”

需要回答一个非常尖锐的问题：

> **为什么 Microsoft / OpenAI / Google / Salesforce / ServiceNow / 其他通用平台不能在自己的平台里直接复制它？**

如果答案只是：

- UI 更漂亮
- workflow 更专业
- 多几个 integration

那么长期壁垒往往不够强。

当然，强 UX 仍然可以是非常好的创业机会，尤其是在模型能力相近、用户需求复杂的情况下；但那属于 **Experience moat**，而不是天然的 vertical moat。

---

## 6. 更有意义的 Agent moat

我们最终把创业 moat 大致归纳为几类：

| 类型 | 核心资产 | 平台复制难度 |
|---|---|---|
| Vertical UI | Product / UX | 低～中 |
| Vertical Workflow | Workflow + integrations | 低 |
| Vertical Intelligence | Domain judgment / decision engine | 中 |
| Vertical World Model | Proprietary state + longitudinal data | 高 |
| Agent Network | Network effects / relationships | 很高 |
| Creator / Content OS | Community + content graph + distribution | 很高 |

因此真正值得优先研究的，通常不是“行业本身”，而是：

> **这个 Agent 是否能积累一个通用平台很难复制的长期资产？**

---

## 7. Creator OS / Community 是另一条重要路线

我们保留 Creator OS / Community 作为一个非常重要、且与 Vertical Intelligence 不同的创业方向。

视频生成是一个很好理解的例子。

在模型能力还不足以稳定生成工业级电影内容时，竞争点仍然高度集中于 model capability，例如：

- 长视频一致性
- 跨镜头 identity consistency
- motion / physics
- storytelling coherence

但随着基础模型能力逐渐提升，竞争可能从：

```text
Model capability
```

迁移到：

```text
Creation experience
Agent-assisted creation
Community
Content graph
Discovery
Remix
Distribution
```

因此真正的产品可能不是一个“视频生成器”，而是一个：

> **Creator Operating System**

它可以让用户长期维护并复用：

```text
Character
World
Style
Voice
Personality
Memory
Workflow
Agent
Content
```

并通过社区形成反馈飞轮：

```text
User
  ↓
Create
  ↓
Content
  ↓
Community
  ↓
Discovery / Remix
  ↓
More Creation
  ↓
More Users
```

Liblib 可以作为这一方向的重要启发：它的价值不只是模型调用，而是模型能力、创作体验、内容供给、社区和分发形成的组合。

因此 Creator OS / Community 的真正 moat 往往来自：

```text
Creator identity
+
Content graph
+
Community
+
Distribution
+
User habit
```

而不仅仅是模型或 Agent 本身。

---

## 8. 三条值得长期关注的 Agent 创业路径

基于目前的讨论，可以把 Agent 创业机会粗略归为三条大路：

### A. Sell Intelligence

> **把 intelligence 放进一个长期存在的 Agent。**

关键词：

```text
Role
World Model
Agency
Responsibility
Memory
Judgment
```

这是最“Agent-native”的方向。

典型目标不是“做一个行业 workflow”，而是创造：

```text
AI Scientist
AI CFO
AI Producer
AI Trader
AI Architect
AI Recruiter
AI Project Manager
AI Underwriter
```

这些名称只有在 Agent 真正拥有对应 Role 所需的 world model、judgment、memory 和 responsibility 时才有意义。

### B. Sell Creation

> **让人更容易创造、驾驭、分享 Agent / content / worlds。**

关键词：

```text
Creator OS
Agent marketplace
Community
Content graph
Remix
Distribution
```

### C. Sell Infrastructure

> **让这些长期存在的 intelligence 可以被创建、部署、运行、治理和迁移。**

这对应另一个正在形成的基础设施方向：

```text
Agent Definition
       ↓ Runtime ABI
Agent Runtime
       ↓ Lifecycle Contract
Agent Management Plane
```

这部分与 `oh-my-agentX` 的核心研究直接相关。

---

## 9. 与 oh-my-agentX 的关系

`oh-my-agentX` 研究的是 Agent 的基础架构边界：

```text
Agent Definition
       ↓
Runtime ABI
       ↓
Agent Runtime
       ↓
Lifecycle Contract
       ↓
Agent Management Plane
```

本文件研究的是创业与产品层：

```text
What intelligence should be created?
What role should it embody?
What world should it model?
What responsibilities should it own?
What moat can accumulate over time?
```

两者的关系不是重复，而是上下游：

```text
oh-my-agentX
    → 如何让长期 Agent 成为一种可定义、可运行、可管理的计算实体

Agent Startup Research
    → 哪些长期 Agent 值得被创造，以及为什么它们能够形成独立公司
```

---

## 10. Current working thesis

截至 2026-08-15，我们当前最值得继续验证的判断是：

> **未来 Agent 创业最重要的机会，不一定来自“给某个行业做一个 Agent workflow”，而更可能来自创造一种通用平台难以简单复制的长期 Intelligence。**

这类 Intelligence 至少应该在以下某一维形成积累：

```text
Persistent World Model
Longitudinal Memory
Role / Responsibility
Domain Judgment
Agent Identity
Network Effects
Creator Community
Content Graph
Distribution
```

因此下一阶段研究应重点问：

1. 哪些 Role 天然需要长期 world model？
2. 哪些 Role 可以让 Agent 真正承担 responsibility，而不只是执行 task？
3. 哪些 Agent 的价值会随着运行时间增长？
4. 哪些 Agent 可以形成 proprietary data / outcome feedback loop？
5. 哪些 Agent 可以形成 agent-to-agent network effects？
6. 哪些 Creator OS / Community 产品可以形成内容和关系网络？
7. 哪些所谓“Vertical Agent”其实只是通用平台上的 workflow template？

**核心原则：不要从“哪个行业能用 Agent”开始，而要从“什么 Intelligence 值得被长期创造出来”开始。**
