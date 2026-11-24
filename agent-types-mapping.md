# 🧩 Agent Types Mapping

### How Copilot Studio, Microsoft Foundry, your own platform, and third-party agents all wire into the four control layers — natively, by configuration, or by federation

[⬅️ Back to Overview](./README.md)

---

## 📑 Table of Contents

- [Why this mapping exists](#-why-this-mapping-exists)
- [The four hosting patterns](#-the-four-hosting-patterns)
- [Four agent types, one governed envelope](#-four-agent-types-one-governed-envelope)
- [Type 1 · Copilot Studio Agents (SaaS)](#-type-1--copilot-studio-agents-saas)
- [Type 2 · Microsoft Foundry Agents (Managed Runtime)](#-type-2--microsoft-foundry-agents-managed-runtime)
- [Type 3 · Platform Agents (BYO Runtime)](#-type-3--platform-agents-byo-runtime)
- [Type 4 · Third-Party Agents (Federated)](#-type-4--third-party-agents-federated)
- [Master mapping matrix](#-master-mapping-matrix)
- [Choosing a pattern](#-choosing-a-pattern)
- [Defense in depth across agent types](#-defense-in-depth-across-agent-types)

---

## 🎯 Why this mapping exists

People most often assume that choosing an AI platform means committing to **one way of building agents**. It doesn't.

Whatever you build with — Copilot Studio, Microsoft Foundry, your own platform, or a third-party tool — **each one plugs into the same four Citadel control layers**. The only thing that changes is **HOW** it connects:

| Connection mode | Meaning |
|-----------------|---------|
| 🟩 **Native / Automated** | The control applies out of the box with little or nothing to wire up |
| 🟪 **Configurable** | The control applies once you make a deliberate setup choice |
| 🟥 **Federated / Emulated** | The control applies by bringing an external runtime under your control planes, bounded by what that runtime exposes |

> [!TIP]
> **Layer 2 does not require Foundry hosting.** Microsoft Foundry acts both as an agent **runtime** (prompt and hosted agents, which inherit its capabilities automatically) and as the **observability plane for agents running anywhere else** — AKS, Azure Container Apps, other clouds, on-premises, or third-party runtimes — which reach it by forwarding **OpenTelemetry GenAI semantic traces** to Foundry-connected Application Insights. That is precisely why every "Configurable" cell in the L2 row below is achievable. See [Layer 2 · Agent Operations](./layer-2-agent-operations.md).

> [!IMPORTANT]
> **Key insight: Agent Management (Layer 3) is the connective tissue.** Once an agent has an identity in Entra Agent ID and appears in Agent 365 with observability enabled, your Layer 4 security and governance controls light up **automatically**. Get agent management right and the security layer comes along almost for free.
>
> This is also what makes the registry **heterogeneous**: whatever the agent type, once registered it lands in the **same registry, the same identity model, the same policy surface, and the same audit trail**. See [Layer 3 · Agent Management](./layer-3-agent-management.md).

---

## 🏗️ The four hosting patterns

Every agent maps to one of four hosting patterns on Azure — then agents get context, tools, and each other. **Mix them freely for any experience.**

| Pattern | Hosting | Dev model | Example |
|---------|---------|-----------|---------|
| **SaaS** | Microsoft-hosted | Low / no-code | Microsoft 365 Copilot · Copilot Studio |
| **Managed Runtime** | Fully managed Azure runtime | Low-code → pro-code | Microsoft Foundry Agent Service |
| **Managed Compute (BYO)** | Your runtime on Azure | Pro-code | AKS · Azure Container Apps |
| **3rd-Party + On-prem** | Federated in | Any type | 3rd-party SaaS / runtime · on-premises |

**And whatever you build, agents never run alone. Every agent gets:**

- 🧠 **Context · IQ** — grounded in your data
- 🧰 **Tools · MCP** — extended by your tools
- 🤝 **Collaboration** — agent-to-agent (A2A)
- 🎛️ **Any model** — freedom of model choice

**Plus agent-level trust, built in:** 🔍 Traces · 📊 Evals · 🎯 Red-teaming · 🚧 Guardrails

---

## 🗺️ Four agent types, one governed envelope

**The four control layers**

| Layer | Purpose | Platform |
|-------|---------|----------|
| 🔷 **L1 · Governance Hub** | Governed model & tool access | *Azure API Management* |
| 🔶 **L2 · Agent Operations** | Telemetry, tracing, AI evals | *Microsoft Foundry · Azure Monitor / Application Insights* |
| 🟢 **L3 · Agent Management** | Agent management & central registry | *Microsoft Agent 365 · Agent 365 SDK* |
| 🛡️ **L4 · Security Foundation** | Threat, posture & data governance | *Defender · Purview · Entra* |

**The four agent types**

| Type | Posture summary |
|------|-----------------|
| **Copilot Studio Agents (SaaS)** | Most layers native; L1 / L2 configurable |
| **Microsoft Foundry (Managed Runtime)** | Deepest native integration across L1–L4 |
| **Platform Agents (BYO Runtime)** | Mostly configurable; L4 native once identity exists |
| **3rd-Party Agents (Federated)** | Federated; configurable where the runtime allows |

**The pattern:** the higher up the Microsoft-managed stack you build, the more of these controls you get automatically. Copilot Studio gives you the most out of the box; your own platform agents you wire up yourself; third-party agents you federate in.

---

## 🟦 Type 1 · Copilot Studio Agents (SaaS)

> **Most layers native — inherits the most automation.**

| | |
|---|---|
| **Hosting** | Microsoft-hosted SaaS with built-in LLMs & tooling |
| **Dev model** | Low / no-code canvas |
| **Posture** | Most layers native; L1 / L2 configurable |

| Layer | Mode | How it connects |
|-------|------|-----------------|
| 🔷 **L1 Gateway** | 🟪 **Configurable** | You point it at your governed tools (MCP) through an **Access Contract** — a setup choice, not automatic. Once connected, baseline security will apply. |
| 🔶 **L2 Operations** | 🟪 **Configurable** | Stream activity telemetry to your Application Insights. Note this is **event-level telemetry, not full `gen_ai.*` tracing**. |
| 🟢 **L3 Management** | 🟩 **Native** | Automatically gets an **Entra Agent ID** and appears in your Agent 365 registry — nothing to wire up. |
| 🛡️ **L4 Security** | 🟩 **Native** | Your Defender posture and Purview data governance attach to that identity **automatically**. |

**Bottom line:** for these agents, governance is essentially **on by default**. Because identity is automatic, your Defender and Purview controls cover them with little to no setup.

> [!IMPORTANT]
> Copilot Studio Agents inherit most security and governance controls automatically from Agent Management through Agent 365 and the security foundation. Usually SaaS agents uses built-in LLMs with variety of tooling options so gateway integration is only needed for tools that are external to the platform. This means that for most scenarios, you get strong security and compliance coverage with minimal configuration effort.
> 
> **Key takeaway:** Focus on connecting external tools through the gateway; the rest of the stack is largely handled for you.

---

## 🟩 Type 2 · Microsoft Foundry Agents (Managed Runtime)

> **Deepest native integration — governance built in across the stack.**

| | |
|---|---|
| **Hosting** | Fully managed Azure runtime + ecosystem |
| **Dev model** | Low-code prompt → pro-code BYO container (Foundry Hosted Agent) |
| **Posture** | Native across L1–L4; only the gateway needs configuring |

| Layer | Mode | How it connects |
|-------|------|-----------------|
| 🔷 **L1 Gateway** | 🟪 **Configurable** | A **Foundry connection** routes your agents to your governed models — Foundry *"Admin-Connected-Models"*. |
| 🔶 **L2 Operations** | 🟩 **Native** | Connect your Application Insights and **tracing plus evaluations turn on automatically — no code**. |
| 🟢 **L3 Management** | 🟩 **Native** | Each **project and each published agent gets its own identity automatically — no stored secrets**. |
| 🛡️ **L4 Security** | 🟩 **Native** | Your posture management, agent inventory, and data governance cover these agents **out of the box**. |

**Bottom line:** across observability, identity, and security the controls are built in — **you only configure the gateway**.

---

## 🟪 Type 3 · Platform Agents (BYO Runtime)

> **Mostly configurable — maximum control, in return for wiring it up yourself.**

| | |
|---|---|
| **Hosting** | BYO framework container on your own platform compute (AKS, ACA) |
| **Dev model** | Pro-code |
| **Posture** | Mostly configurable; **L4 native once Agent Management layer registration exists** |

| Layer | Mode | How it connects |
|-------|------|-----------------|
| 🔷 **L1 Gateway** | 🟪 **Configurable** | Your container calls models and tools through your **Central AI Gateway (APIM)**, with secrets kept in **Key Vault** — the same controls apply as everywhere else. |
| 🔶 **L2 Operations** | 🟪 **Configurable** | Register the Agent with Foundry as `External Agent`, and export **OpenTelemetry GenAI semantic traces** to your Foundry-connected Application Insights; your pro-code SDKs can emit **full `gen_ai.*` spans**. Once in Foundry the agent gets the **same** end-to-end traces, AI evaluations, and quality/safety signals as a Foundry-hosted agent — **without being hosted in Foundry**. Because it relies on an open standard, a wide variety of agentic frameworks are supported, and because it's your code you capture the richest detail. |
| 🟢 **L3 Management** | 🟪 **Configurable** | Use **managed identity or AKS workload identity**, then **register the agent** via the **Agent 365 SDK** to give it an Entra Agent ID, a named sponsor, and a blueprint. |
| 🛡️ **L4 Security** | 🟩 **Native** | Once it's registered in your Agent 365, governance treats it **like any first-party agent**. |

**Bottom line:** **giving the agent an identity is the key step** — it's what switches on all your security and governance.

---

## 🟥 Type 4 · Third-Party Agents (Federated)

> **Federate into the control planes — bounded by what the external runtime exposes.**

| | |
|---|---|
| **Hosting** | Any type (SaaS / platform), hosted on-premises or on other clouds |
| **Dev model** | Any |
| **Posture** | Federated; configurable where the runtime allows |

| Layer | Mode | How it connects |
|-------|------|-----------------|
| 🔷 **L1 Gateway** | 🟪 **Configurable\*** | Point the Agent's **egress at your Governance Hub AI gateway** where it lets you set model and tool endpoints — so your limits and safety apply even off-Azure. |
| 🔶 **L2 Operations** | 🟪 **Configurable** | Register the Agent with Foundry as `External Agent` and leverage Vendor-neutral **OpenTelemetry export** to your Foundry-connected Application Insights, landing the agent in the same observability plane; **level of detail depends on what the agent runtime exposes**. |
| 🟢 **L3 Management** | 🟪 **Configurable** | **Register it into Entra Agent ID / Agent 365 via the Agent 365 SDK** to make it visible and governable. The SDK acts as a sidecar, or directly integrated in the code with minimal changes. In addition to that, a broad partner ecosystem already integrates with it. |
| 🛡️ **L4 Security** | 🟥 **Federated\*** | Once registered with Agent 365 with observability turned on, your security signals are collected and evaluated **to extend to it too**. |

> [!WARNING]
> **\* Bounded by what the source runtime exposes.** How far you can go depends on what the external tool makes available — this is the newest area, so **validate before you commit**.

---

## 📊 Master mapping matrix

**How each agent type connects to each layer**

| Layer | Copilot Studio<br/>(SaaS) | Foundry<br/>(Managed Runtime) | Platform<br/>(Customer-Managed) | 3rd-Party<br/>(Federated) |
|-------|---------------------------|-------------------------------|----------------------------------|---------------------------|
| **L1 Gateway** | 🟪 **Configurable**<br/>Access Contract to gateway models / MCP tools | 🟩 **Native**<br/>Foundry connection ("Admin-Connected-Models") | 🟪 **Configurable**<br/>Key Vault–based contract → APIM | 🟪 **Configurable\***<br/>Point runtime egress at APIM where allowed |
| **L2 Operations** | 🟪 **Configurable**<br/>App Insights telemetry (event-based) | 🟩 **Native**<br/>Auto-tracing + evals on managed runtime | 🟪 **Configurable**<br/>OTEL distro → App Insights (`gen_ai.*`) | 🟪 **Configurable**<br/>OTEL export → App Insights |
| **L3 Management** | 🟩 **Native**<br/>Auto Entra Agent ID, in Agent 365 | 🟩 **Native**<br/>Auto identity per project & per agent | 🟪 **Configurable**<br/>Managed / Workload ID + SDK registration | 🟪 **Configurable**<br/>Register into Entra Agent ID / Agent 365 |
| **L4 Security** | 🟩 **Native**<br/>Defender + Purview linked to identity | 🟩 **Native**<br/>Same as Copilot Studio | 🟩 **Native**<br/>Once identity exists | 🟥 **Federated\***<br/>Once registered (preview, support-list) |

> **Reading the matrix diagonally:** automation concentrates **top-left** (SaaS / managed agents); configuration effort concentrates **bottom-right**. **Identity (L3) is the hinge that lights up L4.** Every cell is achievable.
>
> *\* Bounded by what the source runtime exposes.*

---

## 🧭 Choosing a pattern

It's **not either-or — you mix these**. A single Frontier pillar often combines more than one.

| If you need… | Start with | Why |
|--------------|-----------|-----|
| The fastest path for business makers, AI in the flow of work | **Copilot Studio (SaaS)** | Governance is on by default; identity and security are native |
| Specialist depth inside the employee experience | **Foundry agents published to Microsoft 365** | Pro-code depth without sending employees to another app |
| Scale and control for customer-facing agents without running infrastructure | **Foundry Agent Service (Managed Runtime)** | Deepest native governance; tracing and evals with no code |
| Full control over the framework, autonomous multi-agent workflows | **Managed compute (BYO) on AKS / ACA** | Richest telemetry via `gen_ai.*` OTEL spans; you own the wiring |
| To bring an existing external or on-premises agent estate under control | **3rd-party (federated)** | Register for Agent Management first — that's what makes it visible and governable |

**Sequencing advice for BYO and third-party agents:**

1. **Identity first** — register the agent into Entra Agent ID / Agent 365. This single step unlocks Layer 4.
2. **Then the gateway** — route model and tool calls through APIM with secrets in Key Vault (where supported).
3. **Then telemetry** — export OpenTelemetry into your Foundry-connected Application Insights (where supported).
4. **Then validate** — for third-party runtimes, confirm what the vendor actually exposes before committing.

---

## 🛡️ Defense in depth across agent types

Because coverage differs by agent type, **Citadel's controls deliberately overlap**. When one control can't apply, another holds the line.

| Scenario | Controls that can't apply out of the box | The control that holds |
|----------|-------------------------------------------|------------------------|
| **Agent runs outside Foundry** — e.g. a self-hosted model on a GPU VM | Agent Operations, Security Foundation | 🔷 **Governance Hub** enforces content safety at the gateway (which can run on-premises), because traffic still flows through it as mediator between agent and model + option to integrate Agent 365 for identity and observability that can unlock Security Foundation controls |
| **Microsoft Copilot agents** — traffic doesn't traverse your gateway or Foundry | Governance Hub, Agent Operations | 🟢 **Agent Management (Agent 365)** and 🛡️ **Security Foundation (Defender)** enforce it, on top of Copilot's native protections |

**Same risk, multiple enforcement points — if one control can't apply or is bypassed, another does.**

---

## 🔗 Related guidance

- [Overview — AI Citadel Blueprint](./README.md)
- [Layer 1 · Governance Hub](./layer-1-governance-hub.md) — access contracts, backend contracts, routing
- [Layer 2 · Agent Operations](./layer-2-agent-operations.md) — OpenTelemetry, tracing, evals, guardrails
- [Layer 3 · Agent Management](./layer-3-agent-management.md) — Entra Agent ID and Agent 365 registration
- [Layer 4 · Security Foundation](./layer-4-security-foundation.md) — what identity unlocks
- [Technical Activation Paths](./technical-activation-paths.md) — how to stand each layer up
- [Organizational Alignment & Ownership](./organizational-alignment-and-ownership.md) — who owns the wiring

---

<sub>AI Citadel Blueprint × Frontier Transformation · Microsoft · Global Black Belt</sub>
