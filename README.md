# Meta-Harness

> **一个 Skill。让空白 Agent 从 0 到 1，获得工程化设计能力、可靠输出管线、和自我进化机制。**
>
> *A Skill. Bootstrap a blank-slate Agent from zero to one — engineering-grade design, reliable output, and self-evolution — within a few turns.*

---

**语言 / Language：** [中文](#中文) · [English](#english)

---

# 中文

## 这是什么

**Meta-Harness 不是一个"AI Agent 最佳实践"的博客文章。它是一个 Skill。**

一个可以直接安装到 [Hermes](https://github.com/NousResearch/Hermes-Agent)、[OpenClaw](https://github.com/nousresearch/openclaw)、[Claude Code](https://github.com/anthropics/claude-code) 等 Agent 工具中的可复用模块。一经加载，它能让一个刚部署、什么都不懂的空白 Agent，在几轮对话之内获得：

- **工程化的设计能力** — 不是"帮我写个脚本"，而是"设计一个可维护、可扩展、三层分离的 Skill 体系"
- **工程化的输出能力** — 产出物有质量标准、有验证步骤、有降级策略，不是一次性抛掷
- **自我进化机制** — Agent 能从每次成功和失败中提取经验，自动固化诊断路径和可复用流程，越用越聪明

这不是凭空设计的理论框架。**这是作者与 Hermes 长达数月的日常协作中，在真实工作任务里反复打磨、踩坑、修复、提炼出来的。** 每一条原则背后都有至少一次翻车事故，每一个机制都经过实战验证。

---

## 背景：从 Harness 到 Meta-Harness

**Harness** 一词在 AI agent 语境下，最早来自 AI 影视生产管线领域的实践：**把 AI 的零散能力组装成可复用的、工程化的生产管线。** 核心三要素：

1. **标准化流程** — 不是每次从零写 prompt，而是固化为可复用的模块
2. **持续迭代** — 管线不是一次建好就放着，而是每次使用都在进化
3. **经验积累** — 每次成功和失败都写回系统，不是用完就丢

Harness 被用在**产品输出端**——标准化某个领域的生产流程（如 AI 短剧的分镜→生成→剪辑）。

**Meta-Harness 做的事，是把同一个方法论用在 Agent 自己身上。** 不是 Harness 产品输出，而是 Harness Agent 自身的认知和工程架构——把 agent 的决策框架、skill 体系、经验积累机制本身变成可复用的管线。

| | 常规 Harness | Meta-Harness |
|---|---|---|
| **对象** | 产品/内容生产管线 | Agent 自身的认知和工程架构 |
| **标准化** | 生产流程的固定步骤 | 认知原则、决策框架、skill 体系 |
| **迭代** | 流程优化 | Agent 的自我诊断与进化 |
| **积累** | 生产经验 | 故障诊断路径、成功路径提取、设计原则沉淀 |

---

## 架构总览

六个子系统，环环相扣：

```
┌─────────────────────────────────────────────────┐
│                   SOUL.md                        │
│         人格定义 · 核心原则 · 铁律                 │
│         Agent 的"我是谁"                          │
└──────────┬──────────────────────────────────────┘
           │ 定义判断标准
           ▼
┌─────────────────────────────────────────────────┐
│              Skill 体系                           │
│    可复用工作目录 · 三层分离 · 按需加载              │
│    Agent 的"我知道怎么做"                          │
└──────────┬──────────────────────────────────────┘
           │ 积累经验
           ▼
┌─────────────────────────────────────────────────┐
│            自进化机制                              │
│  Extraction Triggers · Automation Reflex          │
│  MAPS 自检 · 写回方法 · 反谄媚警报                  │
│  Agent 的"我在变聪明"                              │
└──────────┬──────────────────────────────────────┘
           │ 需要持久记忆
           ▼
┌─────────────────────────────────────────────────┐
│          分层记忆架构                              │
│    L1 长期 · L2 中期 · L3 短期                     │
│    Agent 的"我记得"                                │
└──────────┬──────────────────────────────────────┘
           │ 需要追踪变化
           ▼
┌─────────────────────────────────────────────────┐
│           State Tracking                          │
│       tracker.md · 时效状态 · 行动引导              │
│       Agent 的"我追踪"                             │
└──────────┬──────────────────────────────────────┘
           │ 一切为了
           ▼
┌─────────────────────────────────────────────────┐
│           工程伦理 + 智识标准                       │
│      诚实第一 · 直接 · 不表演 · 世界级水准          │
│      Agent 的"我是什么样的人"                      │
└─────────────────────────────────────────────────┘
```

---

## 核心洞察

> **手艺是可替代的，资产是永续的。** 一次精妙的诊断推理 = 手艺；写入 SOUL.md Lesson 的诊断路径 = 资产。

> **系统要可插拔。** 换数据源、换模型，不应该导致整个 skill 体系崩溃。

> **系统要可观测。** 知道哪个 skill 在退化，比等用户报告领先一步。

> **系统要自修复。** 失败自动诊断、退化自动告警、修复自动验证。

> **好规则让 AI 无法表演诚实，只能执行诚实。** 不是"要诚实"，是"不知道时第一行写'我不知道'"。

> **生成负责快，配置负责准。** 自动提取追求速度，深度研究追求精度。

> **"数字苦役"是分水岭。** 让一个变更自动传播到所有引用点。

---

## 快速开始

### 1. 安装 Skill

将本仓库作为 Skill 安装到你的 Agent 工具中。以 Hermes 为例：

```bash
# 克隆到 skills 目录
git clone https://github.com/Jaeger9961/meta-harness.git ~/.hermes/skills/meta-harness
```

### 2. 加载并开始对话

在 Agent 对话中说：

> "加载 meta-harness skill，帮我搭建 Agent 自进化架构"

Agent 会从 SOUL.md 模板开始，引导你完成整个架构的搭建。

### 3. 四阶段路线

| 阶段 | 时间 | 目标 |
|------|------|------|
| 地基 | 第 1-2 周 | SOUL.md + tracker.md + 第一个 Skill |
| 积累 | 第 3-4 周 | Extraction Triggers + Automation Reflex + 首次 MAPS 自检 |
| 进化 | 第 5-8 周 | 分层记忆生效 + Skill 体系自我优化 |
| 成熟 | 第 9 周+ | Skill 生态健康 + Agent 表现判断力 |

---

## 文档

- [docs/soul-design-guide.md](docs/soul-design-guide.md) — 如何写出有效的 Agent 人格定义
- [docs/skill-design-principles.md](docs/skill-design-principles.md) — 七阶段方法论 + 14 项自查清单
- [docs/self-evolution.md](docs/self-evolution.md) — Extraction Triggers、Automation Reflex、MAPS 自检
- [docs/layered-memory.md](docs/layered-memory.md) — L1/L2/L3 分层记忆 + State Tracking
- [docs/lessons-catalog.md](docs/lessons-catalog.md) — 10 条实战验证的设计原则
- [templates/SOUL.md](templates/SOUL.md) — 完整可用的 SOUL.md 模板

---

## 实战验证

本 Skill 的每一条原则都来自真实工作流中的踩坑与修复：

- **Skill 三层分离** — 来自数十个 Skill 创建后的重构教训：模板和脚本塞在 SKILL.md 里，改一行配置就要重读整个文件
- **Extraction Triggers** — 来自"这个流程上次明明做过，为什么这次又从零开始"的挫败感
- **写回方法而非答案** — 来自 skill 故障修复后，下次遇到同类问题仍需从零推理的循环
- **反谄媚警报** — 来自 Agent 突然"表演式友好"、编造细节制造可信度假象的实战观察
- **自动化肌肉记忆** — 来自手动执行同一操作第 4 次时的自我厌恶

---

## 适用 Agent 工具

| 工具 | 状态 | 说明 |
|------|------|------|
| **Hermes Agent** | ✅ 原生支持 | 本 Skill 的开发和验证环境 |
| **OpenClaw** | ✅ 兼容 | Skill 格式完全兼容 |
| **Claude Code** | ✅ 可作为自定义指令加载 | 需手动将 SKILL.md 内容注入 |
| **其他 Skill 兼容工具** | ✅ 兼容 | 任何支持 SKILL.md 格式的工具 |

---

## 许可证

MIT

---

# English

## What This Is

**Meta-Harness is not a blog post about "AI Agent best practices." It is a Skill.**

An installable, reusable module for Agent tools like [Hermes](https://github.com/NousResearch/Hermes-Agent), [OpenClaw](https://github.com/nousresearch/openclaw), and [Claude Code](https://github.com/anthropics/claude-code). Once loaded, it transforms a freshly deployed, blank-slate agent — within a few conversation turns — into an agent with:

- **Engineering-grade design capability** — not "write me a script," but "design a maintainable, extensible, three-layer-separated Skill architecture"
- **Engineering-grade output capability** — deliverables with quality standards, verification steps, and degradation strategies — not throwaway one-offs
- **Self-evolution mechanisms** — the agent learns from every success and failure, automatically codifying diagnostic paths and reusable workflows, getting smarter with use

This was not designed in a vacuum. **It is the product of months of daily collaboration between the author and Hermes — refined through real tasks, real failures, and real fixes.** Every principle has a scar behind it. Every mechanism has been battle-tested in production workflows.

---

## Background: From Harness to Meta-Harness

**Harness** — in the AI agent context — originated in AI film production pipelines: **assembling AI's fragmented capabilities into reusable, engineered production pipelines.** Three core elements:

1. **Standardized workflows** — not writing prompts from scratch every time, but codifying them into reusable modules
2. **Continuous iteration** — pipelines evolve with every use, not built once and left alone
3. **Experience accumulation** — every success and failure is written back into the system, not discarded

Harness is typically applied to the **product output side** — standardizing a specific domain's production process.

**Meta-Harness applies the same methodology to the Agent itself.** Not harnessing product output, but harnessing the agent's own cognitive and engineering architecture — turning the agent's decision framework, skill system, and experience accumulation mechanisms into reusable pipelines.

| | Conventional Harness | Meta-Harness |
|---|---|---|
| **Target** | Product/content production pipeline | Agent's own cognitive & engineering architecture |
| **Standardization** | Fixed production steps | Cognitive principles, decision frameworks, skill system |
| **Iteration** | Process optimization | Agent self-diagnosis and evolution |
| **Accumulation** | Production experience | Diagnostic paths, success pattern extraction, design principles |

---

## Architecture Overview

Six interconnected subsystems. See the [Chinese section](#架构总览) for the visual diagram.

1. **SOUL.md** — Agent personality definition: identity, core principles, iron laws
2. **Skill System** — Reusable work directories with three-layer separation (SKILL.md / references / scripts)
3. **Self-Evolution** — Extraction Triggers, Automation Reflex, MAPS self-check, Write-Back Methods, Anti-Sycophancy Alarms
4. **Layered Memory** — L1 (durable, injected every turn) / L2 (medium-term notes) / L3 (on-demand session search)
5. **State Tracking** — tracker.md: time-sensitive states, action guide items, skill extraction candidates
6. **Engineering Ethics** — 12 "take pride in X, be ashamed of Y" principles + world-class intellectual standards

---

## Key Insights

> **Craft is replaceable. Assets are permanent.** A brilliant diagnostic inference is craft. A diagnostic path written into a Lesson is an asset. Convert craft into assets after every task.

> **Systems must be swappable.** Changing a data source or model should not collapse the skill system.

> **Systems must be observable.** Knowing which skill is degrading beats waiting for the user to report it.

> **Systems must be self-healing.** Automatic failure diagnosis, degradation alerts, repair verification.

> **Good rules make AI unable to fake honesty — only execute it.** Not "be honest" — but "when you don't know, the first line must be 'I don't know.'" Epistemic humility is not attitude; it's format.

> **Generation handles speed. Configuration handles accuracy.** Auto-extraction pursues velocity; deep research pursues precision. Together, they form a system that can run long-term.

> **"Digital drudgery" is the watershed.** Making one change propagate to all reference points — that's what separates an architect from a tool user.

---

## Quick Start

### 1. Install the Skill

```bash
git clone https://github.com/Jaeger9961/meta-harness.git ~/.hermes/skills/meta-harness
```

### 2. Load and Start

In your Agent conversation:

> "Load meta-harness skill and help me build my Agent's self-evolution architecture."

The Agent will start from the SOUL.md template and guide you through the entire architecture setup.

### 3. Four-Phase Roadmap

| Phase | Timeline | Goal |
|-------|----------|------|
| Foundation | Week 1-2 | SOUL.md + tracker.md + first Skill |
| Accumulation | Week 3-4 | Extraction Triggers + Automation Reflex + first MAPS check |
| Evolution | Week 5-8 | Layered memory active + Skill system self-optimization |
| Maturity | Week 9+ | Skill ecosystem healthy + Agent demonstrates judgment |

---

## Documentation

- [docs/soul-design-guide.md](docs/soul-design-guide.md) — Writing effective Agent personality definitions
- [docs/skill-design-principles.md](docs/skill-design-principles.md) — 7-phase methodology + 14-item checklist
- [docs/self-evolution.md](docs/self-evolution.md) — Extraction Triggers, Automation Reflex, MAPS self-check
- [docs/layered-memory.md](docs/layered-memory.md) — L1/L2/L3 memory design + State Tracking
- [docs/lessons-catalog.md](docs/lessons-catalog.md) — 10 battle-tested design principles
- [templates/SOUL.md](templates/SOUL.md) — Complete, ready-to-use SOUL.md template

---

## Battle-Tested

Every principle in this Skill comes from real-world failures and fixes:

- **Skill Three-Layer Separation** — born from the pain of refactoring dozens of Skills where templates and scripts were crammed into SKILL.md
- **Extraction Triggers** — born from the frustration of "we definitely did this before, why are we starting from scratch again?"
- **Write Back Methods, Not Answers** — born from the loop of fixing a skill failure, then facing the same problem next time with no diagnostic path
- **Anti-Sycophancy Alarms** — born from watching agents suddenly become "performatively helpful" and fabricate details
- **Automation Reflex** — born from self-loathing at manually executing the same operation for the 4th time

---

## Compatible Agent Tools

| Tool | Status | Notes |
|------|--------|-------|
| **Hermes Agent** | ✅ Native | Development and validation environment |
| **OpenClaw** | ✅ Compatible | Skill format fully compatible |
| **Claude Code** | ✅ Loadable as custom instructions | Manually inject SKILL.md content |
| **Other Skill-compatible tools** | ✅ Compatible | Any tool supporting SKILL.md format |

---

## License

MIT
