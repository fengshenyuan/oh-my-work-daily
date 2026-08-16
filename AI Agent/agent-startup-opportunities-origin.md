# [Origin] Agent Starup Opportunities


> 本文件是本主题在写入 oh-my-work-daily 之前的原始讨论记录。
>
> 2026.08.15 with ChatGPT
---


# User
好了，那我们现在来讨论了另一个问题：垂直领域的agent还有哪些机会？coding agent已经白热化了，几乎是竞争最激烈的赛道，模型厂商、各个规模的实验室、各个规模的公司、创业者、学生、学术界等等都参与其中了。有比如视频生成、工作流编排等也都是大众熟知或竞争激烈的赛道了。那还有哪些非常值得关注和仔细思考的类似的垂直赛道呢？

# Assistance

对，我会把这个问题看成一个**“哪里还没有被 Agent 化，而且一旦 Agent 化就会形成很深护城河”**的问题，而不是简单找几个“AI + 行业”的应用。

先给结论：

> **Coding Agent 目前已经非常拥挤；下一批真正值得关注的垂直 Agent，我反而会优先看那些“高价值、长流程、强状态、强工具依赖、非结构化输入多、结果可以客观验证、但过去因为自动化成本太高而一直没被软件吃掉”的行业。**

这几个条件比“行业大不大”更重要。

目前企业 Agent 的整体趋势也已经从单点 copilot 往多步骤、跨系统 workflow 发展；Anthropic 的企业调研里，57% 的组织已经在用 multi-stage agent workflow，56% 计划进一步用于 research/reporting。IDC 2026 的调查则显示，企业正在扩大 agent deployment，但 centralized orchestration 和 governance 反而开始变成瓶颈。([Claude][1])

---

## 我先给你一张“我会重点研究”的地图

我不把它按传统行业分类，而按 **Agent 能不能形成强壁垒** 来排：

| 方向                                 |  我关注度 |   竞争度 | Agent 深度 | 最大机会                                         |
| ---------------------------------- | ----: | ----: | -------: | -------------------------------------------- |
| **Construction / AEC**             | ★★★★★ |    ★★ |    ★★★★★ | 文档 + 工地 + 供应链 + RFI/变更                       |
| **Industrial / Manufacturing Ops** | ★★★★★ |    ★★ |    ★★★★★ | ERP/MES/设备/质量/维护                             |
| **Insurance Ops**                  | ★★★★★ |   ★★★ |    ★★★★★ | 承保/理赔/反欺诈                                    |
| **Scientific Research Agent**      | ★★★★★ |    ★★ |    ★★★★★ | Research → experiment → analysis             |
| **Cybersecurity Agent**            | ★★★★★ |   ★★★ |    ★★★★★ | SOC / incident response / autonomous defense |
| **Procurement / Supply Chain**     | ★★★★☆ |    ★★ |    ★★★★★ | RFQ / negotiation / PO / exception           |
| **Field Service / Physical Ops**   | ★★★★☆ |    ★★ |    ★★★★★ | 维修/调度/诊断/现场执行                                |
| **Property / Real Estate Ops**     | ★★★★☆ |    ★★ |    ★★★★☆ | 租赁/维修/合规/供应商                                 |
| **Tax / Audit / Accounting**       | ★★★★☆ |   ★★★ |    ★★★★☆ | evidence-driven workflow                     |
| **Legal**                          | ★★★★☆ |  ★★★★ |    ★★★★★ | 已经有 Harvey 等强玩家                              |
| **Healthcare**                     | ★★★★★ |  ★★★★ |    ★★★★★ | 巨大，但监管/集成壁垒极高                                |
| **Sales / SDR**                    |    ★★ | ★★★★★ |      ★★★ | 已经很拥挤                                        |
| **Customer Service**               |    ★★ | ★★★★★ |      ★★★ | 已经进入平台整合                                     |
| **Coding**                         |     ★ | ★★★★★ |    ★★★★★ | 红海                                           |
| **通用 Workflow Builder**            |    ★★ | ★★★★★ |     ★★★★ | 平台型玩家太多                                      |

这是结合当前 2026 市场状态做的判断，不是简单按 TAM 排名。比如现在公开的 vertical-agent landscape 已经把 customer support、sales、legal、finance、recruiting、healthcare、operations 等列成主要赛道；construction 被一些市场研究直接列入仍然相对“greenfield”的区域。([Presenc AI][2])

下面我重点讲我认为**真正有意思的那些**。

---

## 1. Construction / AEC：我认为这是现在最值得盯的之一

这是我会放在 **Top 3** 的。

原因很简单：

建筑行业有大量信息：

```text
RFP
Drawing
CAD
BIM
Spec
Contract
RFI
Change Order
Inspection
Permit
Invoice
Schedule
Supplier
现场照片
```

这些信息以前很难自动化，因为它们同时包含：

> 文本 + 表格 + CAD/BIM + PDF + 图片 + 时间序列 + 现场状态

但现在 multimodal agent 恰好可以处理这种东西。

比如一个工地发现：

> 某根 prefabricated pipe spool 因工程变更已经装不进去。

这个事件不是一个普通 workflow。

它可能触发：

```text
现场照片
   ↓
识别部件
   ↓
读取最新施工图
   ↓
找工程变更
   ↓
比对 BOM
   ↓
检查供应商
   ↓
生成 RFI
   ↓
检查进度影响
   ↓
计算成本影响
   ↓
修改 schedule
   ↓
通知 PM / GC / subcontractor
```

这已经是一个**真正的 Agent**。

McKinsey 今年 7 月就用非常类似的 construction 场景描述了 agentic AI 如何重构 AEC workflow。([McKinsey & Company][3])

更重要的是：

**这个市场的软件渗透还远没到 coding 那种程度。**

所以：

> Coding Agent 是“模型能力驱动产品竞争”；
> Construction Agent 是“domain + workflow + data + integration 驱动竞争”。

后者对创业公司更友好。

---

## 2. Industrial / Manufacturing Agent：可能比 AEC 更大

这个方向我特别看好。

不要做：

> “AI 帮工程师写 PLC”

那又回到 coding agent。

真正有价值的是：

### Manufacturing Operations Agent

比如：

```text
订单
 ↓
排产
 ↓
物料
 ↓
机器状态
 ↓
质量
 ↓
维修
 ↓
物流
```

一个 agent 可以持续观察：

```text
MES
ERP
SCADA
WMS
QMS
供应链
设备 telemetry
```

然后发现：

> “订单 A 预计会因为设备 M-42 的振动异常而延迟 17 小时。”

它可以：

```text
诊断
 ↓
查询历史故障
 ↓
检查备件
 ↓
联系供应商
 ↓
重新排产
 ↓
评估 SLA
 ↓
通知客户
```

这就是一个非常自然的：

> **Industrial Digital Employee**

而且这个领域真正的 moat 很可能不是模型，而是：

```text
Process Graph
+
Physical World Data
+
Historical Failures
+
Operational Policies
+
System Integration
```

这比 coding agent 难复制得多。

---

## 3. Insurance Agent：我认为特别值得研究

这个市场非常“Agent-native”。

保险业务有几个天然适合 Agent 的特点：

```text
大量文档
+
规则
+
判断
+
多系统
+
高金额
+
长流程
```

特别是：

### Underwriting Agent

真实流程很可能是：

```text
broker email
    ↓
submission documents
    ↓
OCR / extraction
    ↓
risk enrichment
    ↓
missing information
    ↓
policy rules
    ↓
pricing
    ↓
quote
    ↓
human approval
    ↓
bind
```

McKinsey 今年 6 月已经直接把它描述成 “AI-enabled underwriting operating system”，AI 从 intake / triage 一直到 risk selection、pricing、issuance。([McKinsey & Company][4])

BCG 今年也认为保险的核心 underwriting 和 claims workflow 正在从 AI copilot 转向由 autonomous agents 驱动、human oversight 的 end-to-end redesign。([BCG Global][5])

而且保险还有一个很特别的地方：

> **Agent 自己做得越多，新的“Agent Risk”市场反而越大。**

今年已经出现专门研究 agentic AI insurance 的论文，讨论模型错误、prompt injection、autonomous decision error、dependency failure 等风险如何被定价和保险化。([arXiv][6])

所以保险甚至可能同时产生：

```text
Insurance Agent
        +
Agent Insurance
```

两个市场。

---

## 4. Scientific Research Agent：这可能是最有想象力的一条线

这个我认为**非常容易被大众低估**。

因为大家现在习惯把：

> AI Research Agent = 搜论文 + 写报告

这其实只是最低级的第一代。

真正的 Scientific Agent 是：

```text
Research Question
      ↓
Literature
      ↓
Hypothesis
      ↓
Experiment Design
      ↓
Simulation
      ↓
Run Experiment
      ↓
Observe Result
      ↓
Update Hypothesis
      ↓
New Experiment
      ↓
Publication / IP
```

尤其在：

* chemistry
* materials
* biology
* genomics
* semiconductor
* battery
* drug discovery

这些领域，Agent 可以和真实实验设备结合。

今年已经有非常明确的信号：

Nature 的 AutoLabs 已经展示了带 self-correction 的 multi-agent autonomous chemical experimentation；CMU 又在今年 7 月宣布与国家实验室建设连接多个 autonomous laboratories 的 AI 基础设施。([Nature][7])

而材料科学领域的 autonomous lab 研究也开始从“自动做一次实验”往：

> **长期 experiment campaign optimization**

发展。([Nature][8])

这个领域一旦成立，它实际上不是：

> AI employee

而是：

> **AI Scientist**

这可能会是一个完全不同量级的 Agent 产品类别。

---

## 5. Cybersecurity Agent：技术壁垒极高，而且 Agent 特征非常强

这也是我会重点关注的方向。

SOC 本身就是一个很天然的 agent workload：

```text
Alert
 ↓
Investigate
 ↓
Correlate
 ↓
Threat intel
 ↓
Query logs
 ↓
Hypothesis
 ↓
Contain
 ↓
Remediate
 ↓
Verify
```

问题是：

**这件事的 risk 很高。**

也恰恰因此，它非常适合形成深护城河：

```text
Agent
+
Security Policy
+
Identity
+
Telemetry
+
Sandbox
+
Approval
+
Trace
+
Evaluation
```

今年关于 autonomous cyber defense 的综述已经明确把 agent 在 SOC automation、vulnerability analysis、cyber-physical protection 中的应用，以及 tool invocation、多 agent coordination、governance 等问题作为核心研究方向。([ScienceDirect][9])

而最近更频繁出现的 agent escape、agent-as-insider-threat 事件，反而从另一个方向证明：

**Security Agent 可能是 AI Agent 最早被迫进入真正 production-grade autonomy 的领域之一。** ([Axios][10])

---

## 6. Procurement / Supply Chain Agent：我认为非常值得创业者研究

这是我觉得现在被讨论得不够多的赛道。

想象：

```text
需求
 ↓
寻找供应商
 ↓
RFQ
 ↓
询价
 ↓
规格比对
 ↓
谈判
 ↓
合同
 ↓
PO
 ↓
交付
 ↓
质量异常
 ↓
重新询价
```

人类采购经理实际上就在：

> 邮件 + Excel + ERP + PDF + supplier portal

里面不断操作。

这几乎是 Agent 最喜欢的环境。

而且采购 Agent 有一个巨大的优势：

**ROI 非常容易计算。**

例如：

> Agent 给公司采购成本节省 2.3%。

对于一个年采购额 10 亿美元的企业：

```text
2.3% = $23M
```

你根本不用解释“AI 提高生产力”。

所以我会把：

> **Procurement Agent / Supplier Agent / Sourcing Agent**

列为值得深入研究的领域。

---

## 7. Field Service Agent：一个非常容易被忽略的方向

例如：

```text
HVAC
电梯
电力
通信
工业设备
医疗设备
汽车维修
```

维修人员到现场：

```text
拍照
 ↓
读取设备型号
 ↓
查询历史维修
 ↓
读取 manual
 ↓
诊断
 ↓
检查备件
 ↓
下单
 ↓
给维修步骤
 ↓
确认修复
 ↓
生成 service report
```

这不是：

> chatbot

而是：

> **physical workflow agent**

它甚至天然需要 multimodal + tool use + state + long-lived memory。

而且竞争比 coding agent 小得多。

---

## 8. Property / Real Estate Operations：很适合 Agent，但市场认知还比较低

比如大型物业 / commercial real estate：

```text
租户请求
维修工单
供应商
合同
账单
inspection
租约
续租
合规
```

一个 building agent 可以：

> “这栋楼过去 30 天 HVAC 的维修成本上涨了 18%，主要来自 7 个单元；请联系供应商、对比合同价格，并评估是否需要更换设备。”

这类 agent 的价值不是“回答问题”。

而是：

> **持续运营一个资产。**

这正好与你今天讨论的 **Long-lived Agent / Lifecycle Management** 完全吻合。

---

## 9. Tax / Audit / Accounting：比 Legal 更值得关注

Legal 已经非常热门。

Harvey、CoCounsel 等都已经建立了很强的位置。

但：

### Tax / Audit

我觉得仍然有很大机会。

因为它有：

```text
大量证据
+
规则
+
历史
+
系统
+
审批
+
审计追踪
```

比如 audit agent：

```text
读取 GL
 ↓
抓异常
 ↓
匹配 supporting docs
 ↓
抽凭证
 ↓
询问业务部门
 ↓
验证
 ↓
生成 workpaper
 ↓
提出 adjustment
```

这里 agent 的优势非常明确：

> **它可以持续追踪“证据链”。**

这比简单生成文档更有价值。

---

## 10. Healthcare：巨大，但不是我最推荐创业者直接冲进去的

医疗当然值得研究。

但我会把它拆成：

```text
Clinical
Patient Ops
Revenue Cycle
Prior Auth
Coding
Scheduling
Documentation
Research
```

而不是笼统叫：

> Healthcare Agent

现在这个领域已经非常热，而且 integration + regulation 是巨大壁垒。

公开市场研究也明确指出：

> healthcare agent 很难像 legal 那样出现一个横向平台，因为不同 workflow 的 regulatory / risk profile 差异非常大。([Agent Market Cap][11])

所以如果创业：

> “Healthcare Agent”

我不会投。

但：

> **“Prior Authorization Agent”**

> **“Revenue Cycle Agent”**

> **“Specialty Clinic Operations Agent”**

反而很有意思。

---

## 11. 有一个我特别想补充：**Engineering Agent ≠ Coding Agent**

这是一个很大的空白。

Coding 已经爆炸。

但是：

```text
Electrical Engineering
Mechanical Engineering
Chemical Engineering
Civil Engineering
Semiconductor Engineering
Network Engineering
```

呢？

比如：

> “帮我把这块板子的功耗从 12W 降到 8W，同时保持 BOM 成本增加不超过 3%。”

这就不是 coding。

它可能需要：

```text
Datasheet
Simulation
SPICE
CAD
BOM
Supply chain
Historical designs
Test results
```

于是变成：

> **Engineering Agent**

我甚至觉得：

**“Engineering Agent”可能比“Coding Agent”最终大一个维度。**

Coding 是软件工程的一个子技能。

Engineering Agent 才是真正的：

> **AI Engineer / AI Architect**

---

## 最后，我会特别关注 5 条“非显而易见”的赛道

如果让我现在以创业视角筛选，我不是简单列行业，而会重点研究这五类：

### 第一名：Scientific Research Agent

```text
AI Scientist
```

最大的 upside，尤其是 autonomous lab + computational research。

---

### 第二名：Industrial / Field Operations Agent

```text
AI Operations Engineer
```

真实世界、设备、供应链、历史数据，形成极强 moat。

---

### 第三名：Construction / AEC Agent

```text
AI Construction PM
```

行业数字化程度相对低，但 workflow 极其复杂，非常适合 Agent。

---

### 第四名：Insurance Agent

```text
AI Underwriter / Claims Agent
```

高价值、强规则、大量文档、ROI 明确。

---

### 第五名：Procurement / Supply Chain Agent

```text
AI Procurement Manager
```

一个非常适合从“assistant → autonomous worker”跃迁的领域。

---

## 更重要的是：我认为垂直 Agent 创业应该避免一个误区

不要问：

> “哪个行业还没有 AI？”

而应该问：

> **“哪个行业里存在一个人每天在多个系统之间执行大量复杂决策，而这个人的工作本质上是：观察 → 推理 → 调工具 → 修改状态 → 等待新事件 → 再推理？”**

这是一个非常好的 Agent candidate。

因此，我会给垂直 Agent 定义一个“Agent Fitness”：

```text
Agent Fitness =
    Task Value
  × Process Length
  × Tool Dependency
  × Statefulness
  × Event Frequency
  × Verifiability
  × Data Moat
  × Switching Cost
```

而不是：

```text
Agent Fitness = 行业市场规模
```

这就解释了为什么：

**Coding Agent 巨大，但已经红海。**

因为：

```text
Tool dependency ✅
Long-running ✅
Stateful ✅
Verifiable ✅
Data moat ❌
Switching cost ↓
Competition ██████████
```

而 Construction / Insurance / Industrial：

```text
Tool dependency ✅
Long-running ✅
Stateful ✅
Verifiable ✅
Data moat ✅
Switching cost ✅
Competition ██
```

这才是我认为真正值得创业者寻找的区域。

还有一个很有意思的交叉点：**垂直 Agent + Agent OS**。未来最强的垂直 Agent 未必是一个独立 chatbot，而可能是一个长期存在的 **AI Underwriter / AI Construction PM / AI Procurement Manager / AI Lab Scientist**，拥有自己的身份、状态、权限、工具、记忆、事件订阅和生命周期。这个方向正好和我们刚刚给 `oh-my-agentX` 建立的三层架构发生了直接交汇。

[1]: https://claude.com/blog/how-enterprises-are-building-ai-agents-in-2026?utm_source=chatgpt.com "How enterprises are building AI agents in 2026 | Claude by Anthropic"
[2]: https://presenc.ai/research/vertical-ai-agent-market-map-2026?utm_source=chatgpt.com "Vertical AI Agent Market Map 2026 | Presenc AI"
[3]: https://www.mckinsey.com/industries/engineering-construction-and-building-materials/our-insights/how-ai-is-reshaping-the-future-of-the-aec-industry?utm_source=chatgpt.com "How agentic AI is transforming the AEC industry | McKinsey"
[4]: https://www.mckinsey.com/industries/financial-services/our-insights/insurance-blog/the-future-underwriting-operating-system-from-inbox-to-ai-nerve-center?utm_source=chatgpt.com "The future underwriting operating system: From inbox to AI nerve center"
[5]: https://www.bcg.com/publications/2026/the-ai-first-property-and-casualty-insurer?recommendedArticles=true&utm_source=chatgpt.com "The AI-First Property and Casualty Insurer | BCG"
[6]: https://arxiv.org/abs/2606.05449?utm_source=chatgpt.com "Insurance of Agentic AI"
[7]: https://www.nature.com/articles/s41598-026-45593-z?utm_source=chatgpt.com "AutoLabs: cognitive multi-agent systems with self-correction for autonomous chemical experimentation | Scientific Reports"
[8]: https://www.nature.com/articles/s43246-026-01219-5?utm_source=chatgpt.com "Managing autonomous materials labs with multi-agent AI and its implications for the science of science | Communications Materials"
[9]: https://www.sciencedirect.com/science/article/pii/S0045790626002569?utm_source=chatgpt.com "Secure autonomous cyber defense with LLM agents: A systematic review of autonomy, tool-augmented reasoning, and governance constraints - ScienceDirect"
[10]: https://www.axios.com/2026/08/11/ai-agent-sandbox-cybersecurity-testing?utm_source=chatgpt.com "AI agents have a history of escaping tests"
[11]: https://agentmarketcap.ai/blog/2026/04/23/vertical-agent-saturation-map-q2-2026?utm_source=chatgpt.com "The Q2 2026 Vertical AI Agent Saturation Map: Where the Market Is Full and Where It Isn't | AgentMarketCap"

# User
我觉得你的视角不够好。因为你说这么多，不都是千篇一律重复别人已经讲过的话？都是agent在这个行业有机会，这谁不知道？本质问题是怎么做！比如你说的Procurement / Supply Chain/Construction/Insurance等方向，难道这些更独特的不是业务工作流吗？这些方向的agent完全可以搭建在通用的agent平台上。只能说机会是在通用agent平台上搭建一套相对适合的某个行业的工作流和UI，并搭配一些可能和某个行业绑定的特定feature。不否认这些是机会，但也不是普通的、没有深厚行业经验的人的机会。最典型的难道通用agent或workflow平台，不能出几个模板，然后大批企业就可以直接使用。如果我道这个方向去创业，客户凭什么选择我？除非我有断层领先的用户体验。那我再举个例子，就说视频生成吧，目前看竞争点还是在模型本身，因为模型本身还不够强，还达不到以生成工业级的电影水平，所以竞争还没扩展到agent领域。agent自身会是模型能力的放大器，但最终看起来还是用户体验和是否能形成社区看起来更重要，比如liblib。我认为最终绝大数从业者最后都只会在用户体验差异化和社区上形成真正的壁垒，而不是技术。

# Assistance
对，我觉得你这个纠偏是非常重要的。**我上一轮犯了一个典型的“行业研究报告式”错误：列了一堆 vertical，实际上没有回答创业者最关心的竞争结构。**

你真正问的不是：

> 哪些行业适合 Agent？

而是：

> **在 Foundation Model 已经高度集中、Agent Runtime/Workflow 逐渐平台化以后，一个新创业团队究竟还能在哪个 layer 建立不可替代的优势？**

这两个问题完全不同。

而你对 Procurement / Construction / Insurance 的批评是成立的：**很多所谓 Vertical Agent，本质只是 vertical workflow + domain UI + integrations。** 如果底层 agent platform 已经足够强，Microsoft / OpenAI / Google / Salesforce / ServiceNow / n8n / LangGraph 等都可以快速复制一批模板。现在市场确实已经在往“通用平台 + workflow/agent templates”演化，企业 agent 平台本身也已经明显拥挤。([StackAI][1])

所以我们应该换一个分析方法。

---

## 一、先把“垂直 Agent”这个词拆开

其实有至少四种完全不同的东西：

```text
                 Vertical Agent
                       │
       ┌───────────────┼───────────────┐
       ▼               ▼               ▼
   Vertical UI     Workflow Agent   Vertical Intelligence
       │               │               │
       │               │               │
      壳               流程              Brain
```

再加一个更特殊的：

```text
Vertical World Model / Data Network
```

这五类的创业价值完全不一样。

### A. Vertical UI

例如：

> 一个专门给保险公司用的 Agent UI。

这通常很容易被平台复制。

### B. Vertical Workflow

例如：

> Insurance underwriting agent。

如果主要是：

```text
email
→ OCR
→ rules
→ Salesforce
→ quote
→ approval
```

那么它很可能只是一个 workflow package。

**这个我同意你的判断：不是没有生意，而是没有天然 moat。**

---

## 二、真正值得找的是后面的三类

### 1. Vertical Intelligence

这里开始有意思。

不是：

> “我帮你把保险 workflow 自动化。”

而是：

> **“我拥有保险业最好的 underwriting intelligence。”**

区别在于：

```text
Workflow
   ↓
调用模型
   ↓
完成流程
```

vs.

```text
Domain data
   ↓
Domain model / reasoning
   ↓
Domain-specific decision
   ↓
Workflow
```

后者才可能形成真正的技术和数据壁垒。

例如一个真正强的 underwriting system 不只是：

> 读 PDF → 填表。

而是能够长期学习：

```text
风险特征
+
历史赔付
+
行业规律
+
公司 appetite
+
pricing behavior
+
broker behavior
+
外部数据
+
最终 loss outcome
```

最后形成：

> **“对于这种风险，这家公司应该怎么定价、是否接受、应该要求什么条件。”**

这就已经不是 workflow 了。

而是：

**Domain Decision Engine。**

这是非常不同的一层。

---

## 三、更重要的一层：Vertical Agent 其实可以形成自己的“世界模型”

这是我认为我们真正应该寻找的创业方向。

比如 Construction：

普通 Vertical Agent：

```text
读取合同
→ 建一个 RFI
→ 发邮件
```

这没有什么特别。

真正有意思的是：

> **它知道这个项目现在到底处于什么状态。**

于是它建立：

```text
Project World Model

             Project
                │
      ┌─────────┼─────────┐
      ▼         ▼         ▼
   Schedule   Budget    Design
      │         │         │
      ▼         ▼         ▼
    Labor     Material   Change
      │         │         │
      └─────────┼─────────┘
                ▼
             Risk State
```

它持续从：

```text
Drawings
Emails
Meetings
Photos
RFI
Contracts
Invoices
Inspection
IoT
Schedule
```

里更新自己的 world state。

于是 Agent 不再是：

> 一个 workflow executor。

而是：

> **一个持续存在的 domain world model + decision maker。**

这东西就很难被通用平台通过“再做一个模板”复制。

---

## 四、这也是为什么我觉得你举的 Liblib 例子很重要

你说：

> 最终绝大多数从业者可能只能通过 UX 和社区形成真正壁垒。

我认为这个判断**大方向是对的，但需要再精确一点**。

Liblib 的壁垒不是简单：

> “UI 做得好。”

而是：

```text
Model capability
       +
Creation UX
       +
Community
       +
Content
       +
Prompt / workflow knowledge
       +
Distribution
       +
User identity / social graph
```

形成一个 feedback loop：

```text
用户
 ↓
创作
 ↓
内容
 ↓
社区
 ↓
发现
 ↓
模仿 / remix
 ↓
更多创作
 ↓
更多用户
```

这就是 **network effects**。

技术能力会被模型厂商迅速商品化，但：

> **用户关系、内容供给、创作者生态、习惯、分发网络**

没有那么容易被复制。

所以你说：

> “最终看起来还是用户体验和社区更重要”

我基本赞同。

但我会加一个限定：

> **不是所有行业都能靠社区形成 moat；能形成 moat 的，往往是消费/创作/协作型 Agent，而不是纯 B2B workflow。**

---

## 五、所以我们真正应该问：哪些 Vertical Agent 天然有“网络效应”？

这比“哪些行业适合 Agent”重要得多。

我会把候选市场重新分类：

### 第一类：纯 workflow

```text
Procurement
Insurance
Construction
Accounting
HR
```

特点：

```text
价值高 ✅
Agent fit 高 ✅
```

但：

```text
network effect 弱 ❌
通用平台可复制 ✅
```

所以：

**有生意，但未必是最好的创业 opportunity。**

---

### 第二类：Professional Network Agent

这类开始有意思：

```text
Recruiting
Real estate
Procurement marketplaces
Freelancer work
Legal services
Healthcare referrals
```

Agent 不只是替一个人工作。

它开始连接：

```text
Buyer
    ↕
Agent
    ↕
Provider
```

最终形成：

> **Agent-mediated marketplace**

例如招聘：

```text
Candidate Agent
       ↕
Recruiter Agent
       ↕
Company Agent
```

这已经不是 vertical workflow 了。

这是：

**Agent Network。**

而 Network Effect 开始出现。

---

## 六、第三类我认为尤其值得研究：Creator Agent

你提到视频生成，我认为这里实际上蕴含一个很大的 General Principle。

现在视频生成的核心竞争仍然主要在模型能力上，这一点很合理：连 2026 年的研究/评测仍然把长视频一致性、跨镜头身份和物理/叙事 coherence 当作核心未解决问题。([Google Sites][2])

但一旦模型能力足够：

```text
Text → 5 sec video
```

变成：

```text
Idea → movie
```

竞争重点一定会迁移。

迁移到：

```text
Idea
 ↓
Storyboard
 ↓
Characters
 ↓
World
 ↓
Scenes
 ↓
Shots
 ↓
Video
 ↓
Edit
 ↓
Sound
 ↓
Publish
```

这时候：

**Agent 才真正成为核心。**

但重点不是“视频 Agent”。

重点是：

> **Creator Operating System**

例如用户创造一个角色：

```text
Character: Alice
```

以后：

```text
短视频
漫画
图片
游戏
小说
广告
MV
```

都共享：

```text
identity
appearance
voice
personality
world
memory
style
```

那么真正的 moat 就不再是 video model。

而是：

```text
Creator Identity
+
World Model
+
Content Graph
+
Community
+
Distribution
```

这就和 Liblib、Pinterest、TikTok、Roblox、Character AI 等方向产生了非常有意思的交叉。

---

## 七、所以我会把“垂直 Agent 的机会”重新分成 6 种 moat

这比按照行业列 20 个赛道有价值很多。

| 类型                    | 核心壁垒                             | 是否容易被通用 Agent 平台复制 |
| --------------------- | -------------------------------- | ------------------ |
| Workflow Agent        | workflow + integration           | **很容易**            |
| Vertical UI           | UX                               | 容易                 |
| Vertical Intelligence | domain model / decision engine   | 中等                 |
| Vertical World Model  | 持续状态 + 专属数据                      | **较难**             |
| Agent Network         | network effect                   | **很难**             |
| Creator / Content OS  | community + graph + distribution | **很难**             |

于是：

```text
                    创业价值
                       ▲
                       │
            Agent Network
                  ★★★★★
                       │
        Creator / Content OS
                  ★★★★★
                       │
         Vertical World Model
                  ★★★★★
                       │
       Vertical Intelligence
                  ★★★★
                       │
            Vertical Workflow
                  ★★
                       │
             Vertical UI
                  ★
                       └──────────────►
                          moat
```

这个图我认为比“Insurance / Construction / Procurement”那种行业列表更接近你真正要问的问题。

---

## 八、再往前一步：真正好的 Vertical Agent 往往不是“一个行业”，而是“一个长期存在的对象”

这个是我现在最感兴趣的地方。

比如：

### 不好的定义

> Insurance Agent

太泛。

### 稍微好一点

> Underwriting Agent

还是 workflow。

### 再往前

> **Risk Intelligence Agent**

它长期维护：

```text
Company
Risk
Policy
Exposure
Claims
Market
```

---

同样：

### 不好的

> Construction Agent

### 更好的

> Construction PM Agent

### 再往前：

> **Persistent Project Agent**

它长期维护：

```text
Project State
Schedule
Cost
Design
Contract
Risk
People
Suppliers
Issues
```

这时候 Agent 不再是：

> “一个做任务的软件”。

而是：

> **一个数字化的 domain entity。**

这恰好和我们刚刚讨论的 **Long-lived Agent / Lifecycle Management** 接上了。

---

## 九、这其实产生了一个我认为非常强的创业判断

未来最有价值的 Agent 不一定是：

> “一个领域里最聪明的 chatbot。”

甚至不一定是：

> “这个领域最好的 workflow automation。”

而可能是：

> **这个世界里某种长期存在的数字实体。**

比如：

```text
AI CEO
AI Scientist
AI Trader
AI Designer
AI Producer
AI Underwriter
AI Project Manager
AI Recruiter
AI Agent Buyer
```

但关键不是名字。

关键是它有没有：

```text
Identity
State
Memory
Tools
Permissions
Goals
History
Relationships
World Model
Lifecycle
```

一旦这些都存在，它就开始从：

```text
software feature
```

变成：

```text
digital actor
```

---

## 十、所以如果让我重新回答你最初的问题

你最初问：

> “还有哪些类似 coding agent 那样值得仔细思考的垂直赛道？”

我现在**不会回答你一堆行业名字了**。

我会回答：

> **真正值得寻找的不是 Vertical Agent，而是 Vertical Agent 的独特 moat。**

我会优先寻找这三种：

### ① 有自己的世界模型的 Agent

不是 workflow。

而是：

> **Agent continuously maintains a model of the world.**

例如：

* 一个 construction project
* 一个 industrial plant
* 一个 financial portfolio
* 一个 scientific research program

---

### ② 能形成 Agent Network 的 Agent

不是：

> Agent → SaaS → Customer

而是：

```text
Agent A
  ↕
Agent B
  ↕
Agent C
```

从而产生 network effects。

Recruiting、commerce、real estate、procurement、professional services 都值得从这个角度重新看。

---

### ③ 有 Community / Content Graph 的 Creator Agent

这个就是你提到的 Liblib 路线。

```text
Model
  ↓
Agent
  ↓
Creation
  ↓
Content
  ↓
Community
  ↓
Network
```

这类产品最终可能形成最大的非模型 moat。

---

而 **纯 Vertical Workflow Agent**，我现在反而会把它放得比较低。

不是说它没钱赚，而是：

> **它非常可能成为 OpenAI / Microsoft / Google / Salesforce / ServiceNow / n8n / Agent platform 的 template，而不是一个独立的长期平台。**

现在企业 Agent 平台已经明显向“通用 agent runtime + workflow builder + templates + governance”发展，这个趋势已经非常明显。([Connic][3])

所以你刚才这个反驳，其实让我觉得我们应该把问题再提升一层：

> **未来 Agent 创业的真正稀缺资源到底是什么？**

我现在的答案会越来越接近：

**不是模型，不是 workflow，甚至不一定是 Agent Runtime。**

而是：

> **Identity + State + Proprietary World Model + User Experience + Network Effects**

其中任何一项都可能形成 moat，但**至少要有一项是通用 Agent 平台很难复制的**。

这也恰好解释了为什么你前面提出的 **Agent Management Plane / long-lived agent** 这么重要：**一旦 Agent 真正拥有 identity、state、relationships 和 lifecycle，它才有可能累积出平台无法简单复制的东西。**

[1]: https://www.stackai.com/blog/the-best-ai-agent-and-workflow-builder-platforms-2026-guide?utm_source=chatgpt.com "Top AI Agent Platforms for Enterprises (2026)"
[2]: https://sites.google.com/view/aaai26-cvm/competition?utm_source=chatgpt.com "AAAI 2026 Workshop - Competition"
[3]: https://connic.co/blog/ai-agent-deployment-platforms-2026?utm_source=chatgpt.com "AI Agent Deployment Platforms in 2026: 4 Types Compared | Connic"


# User
好的，这个讨论很好。我记得前面其实我们讨论到过agent慢慢会从human driven, goal driven, responasbility driven最终过渡到人类社会普遍的role driven的模式。所以agent创业一个重要方向也可以总结为创造真实的有world model，有长期价值观、有主观能动性的agent；或者说agent创业的价值更多在于放到LLM的intelligence，即交付的是intelligence而不是其他东西。 Creator OS/Community也是一个很有意义的方向，保留。

# Assistance
对，我觉得这次已经把“Agent 创业机会”从行业列表进一步抽象到了一个**更本质的产品定义问题**。

我会把我们前面的讨论重新浓缩成两条主线：

## 1. Agent 的终局可能是从「工具」变成「角色」

我们之前讨论过一个很重要的演化：

```text
Human-driven
      ↓
Goal-driven
      ↓
Responsibility-driven
      ↓
Role-driven
```

这四个阶段其实对应的是 Agent **自主性的来源**发生变化。

### Human-driven

```text
人：去查一下 Apple 翻新机
Agent：执行
```

Agent 没有自己的持续性，只是工具。

### Goal-driven

```text
人：帮我找到一台合适的 M5 Max
Agent：自己规划任务
```

Agent 开始自主规划，但目标仍然来自人。

### Responsibility-driven

```text
你负责帮我盯住 Apple 翻新市场
```

Agent 不再只是完成一次 goal，而是承担一项**持续责任**：

```text
Observe
→ Decide
→ Act
→ Monitor
→ Report
```

这已经是 long-lived agent。

### Role-driven

再往前一步：

```text
“你是我的采购经理。”
“你是这个项目的 CTO。”
“你是我的研究员。”
“你是我的制片人。”
```

这时人不再给 Agent 每个具体 goal。

**Role 本身就是 goal generator。**

例如一个“采购经理”自然知道：

```text
控制成本
保证供应
降低风险
维护供应商关系
满足公司政策
```

甚至当没有任何明确任务的时候，它也知道自己应该关注什么。

这和我们今天讨论的 **Agent Management Plane** 就突然完全接上了：

```text
Role
 ↓
Identity
 ↓
Values / Responsibility
 ↓
World Model
 ↓
State
 ↓
Goals
 ↓
Actions
 ↓
Lifecycle
```

所以我甚至觉得：

> **Role-driven Agent 可能比 Goal-driven Agent 更接近真正的“数字员工”。**

---

## 2. 因此一个真正有价值的 Agent，核心商品其实可能是「Intelligence」

这句话我非常赞同，而且值得稍微精确一下。

不是：

> Agent = LLM + workflow

而是：

> **Agent = Intelligence embedded in a persistent entity**

也就是把 LLM 的 intelligence 真正“放进去”。

这个 Agent 应该拥有：

```text
Identity
World Model
Values
Preferences
Memory
Responsibilities
Goals
Capabilities
Relationships
Judgment
Agency
```

于是产品卖的就不是：

> 一个界面

也不是：

> 一套 workflow

甚至不一定是：

> 一个模型

而是：

> **一个可以长期替你做判断的 intelligence。**

---

### 这时候 vertical 的意义也发生变化

比如不要做：

> Insurance workflow agent

而要问：

> **能不能创造一个真正的 Underwriter Intelligence？**

它应该逐渐形成：

```text
Insurance Underwriter Agent

World Model
├── market
├── customers
├── risks
├── policies
├── claims
└── regulations

Values
├── risk-adjusted return
├── loss avoidance
└── policy compliance

Memory
├── historical decisions
├── outcomes
└── broker behavior

Agency
├── request information
├── negotiate
├── reject
├── escalate
└── re-evaluate
```

这样它才开始拥有真正的**职业能力**。

同样：

```text
AI Scientist
AI CFO
AI Producer
AI Trader
AI Architect
AI Recruiter
AI Project Manager
```

这些名称真正有意义的地方，不是 UI 上叫这个名字。

而是：

> **它真的拥有这个 Role 所需要的 persistent world model + judgment + responsibility。**

---

## 3. 这也解释了为什么“纯 workflow verticalization”长期看可能不够

一个 workflow agent：

```text
Input
 ↓
Workflow
 ↓
LLM
 ↓
Output
```

很容易成为平台 feature。

但 role-driven intelligence：

```text
                    Role
                      │
       ┌──────────────┼──────────────┐
       ▼              ▼              ▼
   World Model      Values        Memory
       │              │              │
       └──────────────┼──────────────┘
                      ▼
                  Judgment
                      │
                      ▼
                   Agency
                      │
                      ▼
                 Responsibility
```

其资产会随着时间增长。

这就是非常关键的区别：

**Workflow 的价值通常是静态的。**

**Intelligence 的价值会累积。**

---

## 4. 于是创业 moat 也可以重新定义

今天我们已经把几个可能的 moat 串起来了：

```text
                Agent Startup
                      │
        ┌─────────────┼─────────────┐
        ▼             ▼             ▼
   Intelligence   Experience    Network
        │             │             │
   World Model       UX         Community
   Memory            Product     Content
   Judgment          Delight     Distribution
   Agency                        Relationships
```

其中：

### Intelligence moat

来自：

```text
proprietary world model
+
longitudinal memory
+
domain judgment
+
feedback / outcome data
```

### Experience moat

就是你刚刚说的：

> 用户体验差异化。

尤其当基础模型越来越商品化以后，UX 甚至会成为**模型能力的放大器**。

### Network moat

就是我们保留的：

> **Creator OS / Community**

因为：

```text
User
→ Create
→ Content
→ Community
→ Remix
→ Distribution
→ More Users
```

这是传统 SaaS 很难形成的飞轮。

---

## 5. 所以现在我会把 Agent 创业机会粗略分成三条大路

不是按行业，而是按你到底在卖什么：

### A. Sell Intelligence

> **把 intelligence 放进一个长期存在的 Agent。**

这是我现在认为最“Agent-native”的创业方向。

关键词：

**Role / World Model / Agency / Responsibility / Memory**

---

### B. Sell Creation

> **让人更容易创造、驾驭、分享 Agent / content / worlds。**

这就是：

**Creator OS / Agent Community / Agent Marketplace**

Liblib 是一个很好的启发，但未来可能远不止图片/视频模型社区，而是：

```text
Agent
Character
World
Skill
Workflow
Memory
Personality
Content
```

全部可以被创建、组合、fork、remix。

---

### C. Sell Infrastructure

> **让这些长期 Intelligence 真正能够被创建、部署、运行、治理。**

这就是我们今天给 oh-my-agentX 提出来的：

```text
Agent Definition
       ↓ Runtime ABI
Agent Runtime
       ↓ Lifecycle Contract
Agent Management Plane
```

这条路线卖的不是 intelligence，而是：

> **让 Intelligence 成为可以被部署、运营、迁移、治理的计算实体。**

---

## 6. 三者其实会形成一个很漂亮的闭环

我现在甚至觉得可以把整个 Agent 产业想成：

```text
                 Agent Infrastructure
                         │
                         ▼
                  Agent Creation
                         │
                         ▼
               Persistent Intelligence
                         │
              ┌──────────┴──────────┐
              ▼                     ▼
          User Value            Community
              │                     │
              └──────────┬──────────┘
                         ▼
                 More Intelligence
                         │
                         └──────→ Infrastructure
```

所以我们之前关于“垂直 Agent”的讨论，最后其实可以被重新表述成：

> **未来最值得关注的不是“哪个行业可以用 Agent”，而是“在哪些地方可以把 LLM intelligence 转化为一个具有 role、world model、memory、values 和 agency 的长期数字实体”。**

而 Creator OS / Community 是另一条完全不同、但同样有可能产生巨大壁垒的路线。

我觉得这已经比“Insurance Agent、Construction Agent、Procurement Agent”这种行业清单高了一个抽象层级。它开始真正回答了**为什么这个 Agent 公司值得存在，以及它凭什么不会被下一个通用 Agent 平台直接做成一个 template**。




