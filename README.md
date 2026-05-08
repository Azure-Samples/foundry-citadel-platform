# 🏰 Foundry Citadel Platform

### A Unified, Layered Approach to AI Security and Compliance

[![Microsoft](https://img.shields.io/badge/Microsoft-AI%20Governance-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://aka.ms/foundry-citadel)
[![IDC Leader](https://img.shields.io/badge/IDC%20MarketScape-Leader%202025--2026-00A86B?style=for-the-badge)](https://learn.microsoft.com/en-us/azure/ai-foundry/control-plane/overview)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE.md)

Foundry Citadel Platform represents Microsoft's comprehensive, layered architecture for AI governance, designed to enable enterprises to scale AI innovation while maintaining trust, security, and compliance. This document provides an in-depth analysis of the technical approach, strategic value proposition, and competitive landscape for Microsoft's layered AI governance solution.

> [!NOTE]
> The purpose of Foundry Citadel Platform is to provide opinionated, pre-built patterns for AI governance that leverage Microsoft's unique capabilities and ecosystem. It is not intended to be a one-size-fits-all solution, but rather a proven architectural approach that can be adapted and extended based on specific organizational needs and risk profiles.

---

## 📑 Table of Contents

- [Executive Summary](#-executive-summary)
- [Unified Technical Approach](#-unified-technical-approach-to-microsofts-layered-ai-governance)
- [Layer 1: Governance Hub](#-layer-1-governance-hub--runtime-enforcement-plane)
- [Layer 2: AI Control Plane](#-layer-2-ai-control-plane--observability-and-compliance)
- [Layer 3: Agent Identity](#-layer-3-agent-identity--agent-365)
- [Layer 4: Security Fabric](#-layer-4-security-fabric--unified-protection-across-all-layers)
- [Community & Ecosystem Extensions](#-community--ecosystem-extensions)
  - [Agent Governance Toolkit — Layer 2 Extension](#agent-governance-toolkit-agt--layer-2-extension)
- [Conclusion](#-conclusion-the-strategic-value-of-microsofts-layered-approach)
- [Key Resources](#-key-resources-and-references)

## 📋 Executive Summary

### ⚠️ The AI Governance Crisis

The enterprise AI landscape in 2026 stands at a critical inflection point. With 20% of all data breaches now directly attributed to unmanaged Shadow AI usage, and 95% of unmanaged GenAI pilots failing to reach production due to lack of governance, organizations face an unprecedented challenge: how to scale AI innovation while maintaining trust, security, and compliance.

### 🏆 Microsoft's Strategic Position

In January 2026, Microsoft was named a **Leader** in the IDC MarketScape for Worldwide Unified AI Governance Platforms 2025–2026, recognized for its end-to-end governance spanning traditional machine learning, generative AI, and agentic AI systems. This recognition validates Microsoft's comprehensive approach to AI governance as both a technical and strategic imperative.

The market trajectory underscores the urgency: Gartner projects that spending on AI data governance will reach $492 million in 2026 and surpass $1 billion by 2030, with fragmented AI regulation extending to 75% of the world's economies by 2030. Organizations deploying AI governance platforms are 3.4 times more likely to achieve high effectiveness in AI governance than those that do not.

### 🏛️ Architectural Philosophy: Separation of Concerns with Unified Oversight

The four layers are not isolated silos—they form an integrated architecture grounded in the principle of **separation of concerns with unified oversight**. Each layer owns a distinct governance responsibility, yet all layers interlock to deliver end-to-end trust:

*   🔷 **Layer 1 – Governance Hub** acts as the physical gateway: a hub-and-spoke deployment where a centrally managed AI gateway (Azure API Management) enforces runtime policies—identity validation, token rate limiting, content filtering, and cost attribution—while spoke environments give each business unit autonomous development within guardrails.

*   🔶 **Layer 2 – AI Control Plane** sits above the gateway to provide the observability and compliance brain. Microsoft Foundry Control Plane continuously evaluates agent behavior, captures end-to-end traces, runs automated red-teaming, and powers fleet operations dashboards—turning raw telemetry from every spoke into actionable governance insights.

*   🟢 **Layer 3 – Agent Identity (Agent 365)** ensures that every agent, whether built in-house or discovered as shadow AI, is a first-class enterprise citizen. Unique identities issued through Microsoft Entra ID, combined with sponsorship models, lifecycle controls, and access packages, mean that no agent operates anonymously at scale.

*   🛡️ **Layer 4 – Security Fabric** weaves real-time protection across the other three layers. Microsoft Defender provides AI-specific threat intelligence and jailbreak detection, Microsoft Purview enforces data governance and PII protection, and Microsoft Entra orchestrates identity-driven access control—together closing the loop from policy definition to runtime defense.

This layered separation means teams can evolve any single capability—upgrade the gateway, add new compliance evaluators, onboard new agent types, or adopt emerging security detections—without destabilizing the rest of the governance stack. The result is an architecture that scales from 10 to 10,000 agents while keeping governance both comprehensive and composable.

### 🎯 Strategic Value Proposition

This layered approach enables enterprises to:

*   📈 Scale from 10 to 10,000 agents with consistent governance and security.
*   ⚡ Reduce compliance bottlenecks through automated policy enforcement at runtime.
*   🚀 Achieve faster time-to-value with pre-built, proven patterns.
*   💰 Lower regulatory expenses by 20% through effective governance technologies.
*   🔄 Maintain continuous compliance as AI systems and regulations evolve.

***

## ⚙️ Unified Technical Approach to Microsoft's Layered AI Governance

### 🔀 The Governance-Velocity Paradox

The fundamental challenge facing enterprises is what Microsoft terms the “Governance-Velocity Paradox.” Compliance traditionally slows innovation, yet AI's transformative potential means enterprises cannot afford to choose between speed and safety. As AI agents move from chat to act and from few to thousands, the stakes escalate exponentially.

Traditional governance approaches create critical bottlenecks:

*   ❌ Manual Risk Assessments: Time-consuming and lacking standardization
*   ❌ Scattered Evaluation Tools: Fragmented across different teams and systems
*   ❌ Unclear Governance Requirements: Ambiguous policies difficult to operationalize
*   ❌ Implementation Gaps: Policies rarely map cleanly to real-world technical implementation

The result: delays that frustrate both governance teams and developers, slowing AI adoption and increasing organizational risk.

### 🤝 The Collaboration Challenge

As AI systems grow from few agents to many, the need for collaboration between different agents, tools, and data becomes key to reusing investments in quality agents. This collaboration typically spans cross-business units and domains to achieve better return on investment and accelerate adoption.

Effective AI governance demands multiple stakeholders collaborating effectively:

*   👔 Compliance Officers & Chief AI Officers: Must determine what needs to be assessed to comply with company policies and regulations
*   ☁️ Cloud Ops Teams: Need to understand how to implement controls and monitor compliance at runtime & establish landing zones for AI workloads
*   👨‍💻 AI Developers & Engineering Teams: Need to operationalize these requirements by generating the right qualitative and quantitative evidence

### 💨 From Bottlenecks to Acceleration

The transformation from traditional to Microsoft's approach:

| Traditional Approach      | Foundry Citadel Platform         |
| ------------------------- | -------------------------------- |
| ❌ Manual risk assessments | ✅ Automated compliance checks    |
| ❌ Scattered tools         | ✅ Unified observability platform |
| ❌ Unclear requirements    | ✅ Codified governance contracts  |
| ❌ Implementation gaps     | ✅ Pre-built, proven patterns     |
| ❌ Friction between teams  | ✅ Streamlined collaboration      |
| ❌ Slow deployment cycles  | ✅ Rapid, repeatable deployments  |

This transformation enables organizations to move from AI experiments to AI at scale, with compliance automated, observability centralized, and policies as code.

***

## 🛠️ Detailed Technical Approach: Layer-by-Layer Analysis

### 🔷 Layer 1: Governance Hub – Runtime Enforcement Plane

#### 📌 Overview and Purpose

The Governance Hub serves as the runtime enforcement layer that mediates AI traffic between agents and LLMs, tools, and other agents. It addresses the critical reality that in an AI system, three primary assets must be governed:

*   🧠 **LLMs:** Provide the brain for AI agents
*   🧰 **Tools and Knowledge:** Allow agents to be grounded with the ability to act
*   🤖 **External Agents:** Enable collaboration as AI systems grow

Without runtime governance, organizations face:

*   💸 Unpredictable costs
*   ⚠️ Reliability issues
*   🔓 Security threats
*   😤 Developer friction
*   😱 Governance nightmares

#### 🧱 Core Components

*   🌐 **Unified AI Gateway** (Azure API Management): Single control point for models, tools, and agents
*   📖 **Universal Registry** (Azure API Center): Centralized catalog for discovery
*   🛡️ **Enforcement Capabilities:**
    *   🔑 Identity validation
    *   ⚙️ Smart operations (token rate limiting, semantic caching, cost attribution)
    *   🚨 Safety (content filtering, prompt injection protection, PII detection)

#### 🏛️ Architectural Philosophy: Separation of Concerns with Unified Oversight

Microsoft's architectural philosophy addresses the governance-velocity paradox through a hub-and-spoke deployment model that provides:

<details>
<summary>🔹 <b>Central Governance Hub</b> – Deployed centrally to serve as the <b>runtime</b> command center</summary>

*   Unified AI gateway for all model, tool, and agent access
*   Universal AI registry for centralized catalog and discovery
*   Centralized logging, monitoring, and policy enforcement systems
*   Shared infrastructure that every project leverages

</details>

<details>
<summary>🔹 <b>Agent Environment Spokes</b> – Deployed multiple times, one for each business unit or use case</summary>

*   Fully self-contained and secure with dedicated compute, storage, data, and dependent services
*   Teams can work autonomously without stepping on each other's toes
*   Each spoke connects back to the hub for centralized governance and observability

</details>

This architecture delivers “local freedom” in each project area under a common governance framework enforced by the hub.

#### 📡 Hub-and-Spoke Deployment Model

The deployment model consists of two primary components:

<details>
<summary>🔸 <b>AI Governance Hub (Central Deployment)</b></summary>

*   One deployment governing both production and non-production environments
*   Or two deployments (one for production, one for non-production) with ability to add more per requirements
*   Enforces runtime policies-as-code for all AI interactions across the organization
*   Platform-level observability & audit-trail: Centralized performance metrics, usage tracking, with optional request/response logging for audit and debugging
*   📎 Guidance available at: <https://aka.ms/ai-hub-gateway>

</details>

<details>
<summary>🔸 <b>Agents Environment (Spoke Deployment)</b></summary>

*   Deployed at spokes with many deployments across the organization
*   One deployment per business unit or use case
*   Accelerates development through templated deployment that is configurable
*   📎 Guidance available at: <https://github.com/Azure/AI-Landing-Zones>

</details>

#### 🔗 Integration with Microsoft AI Governance Stack

| Layer | Integration |
|-------|-------------|
| 🔶 **Layer 2** (AI Control Plane) | Foundry Control Plane relies on the runtime AI Gateway for policy enforcement and collects telemetry for observability and compliance |
| 🟢 **Layer 3** (Agent Identity) | Agent 365 identities are validated at the gateway for access control and policy enforcement |
| 🛡️ **Layer 4** (Security Fabric) | Defender for API security as added layer of security and threat intelligence |

***

### 🔶 Layer 2: AI Control Plane – Observability and Compliance

#### 📌 Overview and Strategic Importance

Powered by Microsoft Foundry Control Plane, this layer automates trust and provides visibility, governance, and control for AI agents, models, and tools across the enterprise.

#### 🧱 Core Functionalities

*   📋 **Controls:** Define and enforce AI evaluations and compliance policies
*   🔭 **Observability:**
    *   Agent-level: Execution traces, performance monitoring, debugging tools
    *   AI Evaluations: during development and in production
*   🔐 **Security:**
    *   Zero trust architecture
    *   Integration with Microsoft security fabric and Agent 365 identity platform
    *   AI Red Teaming
    *   Drift monitoring
*   🚀 **Fleet Operations:**
    *   Track 100% of registered agents
    *   Manage activation and lifecycle
    *   Visualize fleet health and anomalies

#### 🤝 Integration with Partner Ecosystem

| Partner | Capabilities |
|---------|--------------|
| **Credo AI** | Policy-to-code translation, governance-ready artifacts, real-time evaluator feedback |
| **Saidot** | EU AI Act-focused risk evaluations, dataset simulation, and compliance mapping |
| **[Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit)** | In-process policy runtime engine, per-action tool call governance, MCP request/response scanning, continuous trust scoring, framework-agnostic SDK (.NET/TS/Rust/Go) |

#### 🔗 Integration with Microsoft AI Governance Stack

| Layer | Integration |
|-------|-------------|
| 🔷 **Layer 1** (Governance Hub) | Relies on runtime telemetry from the AI Gateway for observability and compliance monitoring |
| 🟢 **Layer 3** (Agent Identity) | Uses identity information from Agent 365 for access control and compliance enforcement |
| 🛡️ **Layer 4** (Security Fabric) | Integrates with Defender for threat intelligence and Purview for data governance insights |

***

### 🟢 Layer 3: Agent Identity – Agent 365

#### 📌 Overview and Strategic Significance

Transforms agents into enterprise assets with unique identities, lifecycle management, and access controls. Addresses shadow AI and enables scale with trust.

#### 🧱 Core Capabilities

*   🆔 **Agent Identity Platform** (Microsoft Entra ID):
    *   Unique agent identities
    *   Shadow agent detection
    *   Lifecycle and ownership management
    *   Sponsorship model for human accountability
*   🔐 **Access Management:**
    *   Access packages
    *   Role-based and attribute-based access control
    *   Expiration and review workflows

#### 🔗 Integration with Microsoft AI Governance Stack

| Layer | Integration |
|-------|-------------|
| 🔷 **Layer 1** (Governance Hub) | Relies on runtime identity enforcement from the AI Gateway |
| 🔶 **Layer 2** (AI Control Plane) | Ability to register Foundry Agent identities with Agent 365 for unified identity management and compliance enforcement |
| 🛡️ **Layer 4** (Security Fabric) | Integrates with Microsoft Entra for identity governance and with Defender for threat detection and Purview signals based on agent behavior |

***

### 🛡️ Layer 4: Security Fabric – Unified Protection Across All Layers

#### 📌 Overview

Provides real-time defense against AI-specific threats and integrates across all governance layers.

#### 🧱 Core Components

<details>
<summary>🛡️ <b>Microsoft Defender</b></summary>

*   Threat intelligence for AI & API attack vectors
*   AI-specific posture management
*   Real-time jailbreak detection
*   Prompt injection protection

</details>

<details>
<summary>📚 <b>Microsoft Purview</b></summary>

*   Data governance and labeling
*   PII detection and protection
*   Compliance automation for 100+ frameworks

</details>

<details>
<summary>🔐 <b>Microsoft Entra</b></summary>

*   Agent and application identity platform
*   Access control and lifecycle automation
*   Shadow agent discovery

</details>

#### 🌐 Unified Security Architecture

*   🔄 Coordinated threat response across Defender, Entra, and Purview
*   👁️ End-to-end visibility and audit trails
*   ⚡ Real-time protection and compliance by design

#### 🔗 Integration with Microsoft AI Governance Stack

| Layer | Integration |
|-------|-------------|
| 🔷 **Layer 1** (Governance Hub) | Defender provides runtime protection for the AI Gateway, while Purview enforces data governance policies at the gateway level |
| 🔶 **Layer 2** (AI Control Plane) | Defender and Purview provide security insights and compliance monitoring for agent behavior, while Entra ensures identity governance |
| 🟢 **Layer 3** (Agent Identity) | Entra provides identity governance for agents, while Defender monitors for identity-based threats and Purview enforces data governance policies based on agent access and behavior |

> [!TIP]
> Microsoft Defender can surface security signals in Foundry Control Plane and Agent 365 allowing different teams to collaborate on threat detection and response.

***

## 🧩 Community & Ecosystem Extensions

The Citadel architecture is designed to be extended. Open-source toolkits can plug into specific layers to add governance capabilities that complement the platform.

### Agent Governance Toolkit (AGT) — Layer 2 Extension

The [Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit) is an open-source (MIT) project that extends **Layer 2: Agent Control Plane** with a comprehensive **policy runtime engine** that operates inside the agent process itself. While the Foundry Control Plane provides fleet-level observability and compliance from above, AGT provides per-action policy evaluation, continuous trust scoring, and tamper-evident audit logging from within the agent runtime, regardless of which agent framework is selected (Semantic Kernel, AutoGen, LangGraph, custom).

#### 🔶 Role in Layer 2: Agent Control Plane

AGT extends the AI Control Plane by pushing policy enforcement to the point of execution:

| Control Plane Capability | Foundry Control Plane | AGT Policy Runtime |
|--------------------------|----------------------|-------------------|
| **Scope** | Fleet-wide observability and compliance | Per-agent, per-action policy decisions |
| **Enforcement point** | Post-hoc evaluation and dashboards | Inline, pre-execution (blocks before action fires) |
| **Latency** | Async telemetry analysis | Sub-millisecond (<0.1 ms) synchronous |
| **Policy granularity** | AI evaluations, drift monitoring | Tool call allow/deny, MCP request/response filtering, PII/CRI blocking |
| **Trust model** | Agent registration and lifecycle | Continuous scoring (0-1000) with automatic revocation |
| **Runtime coupling** | Framework-agnostic (telemetry consumers) | Framework-agnostic (SDK wraps any runtime) |

Together, Foundry Control Plane and AGT provide both the "observe and evaluate" and "intercept and enforce" halves of agent governance within Layer 2.

#### 🔗 Integration with Other Citadel Layers

While AGT lives primarily in Layer 2, it integrates with the full Citadel stack:

| Layer | How AGT Integrates |
|-------|-------------------|
| 🔷 **Layer 1** (Governance Hub) | AGT loads policy bundles from Azure Key Vault or APIM-distributed config. Gateway rules at the network boundary and AGT rules inside the agent both must pass for an action to proceed (defense-in-depth). |
| 🔶 **Layer 2** (AI Control Plane) | **Primary home.** AGT's policy runtime engine, MCP Security Gateway, and trust scoring operate here. Governance telemetry (policy decisions, trust changes, interceptions) exports to Event Hub and Application Insights via a Citadel audit exporter, with `x-ms-request-id` correlation linking to APIM traces. |
| 🟢 **Layer 3** (Agent Identity) | AGT's Ed25519/SPIFFE runtime identities federate with Entra Agent User via attestation-based binding. Trust scores surface as risk labels in A365 telemetry. |
| 🛡️ **Layer 4** (Security Fabric) | AGT's `data_classification` labels align with Purview sensitivity labels. MCP response scanning blocks PII/CRI leaks before they reach LLM context, complementing Defender's threat detection. |

#### 🛠️ Key Capabilities AGT Adds to Layer 2

*   **MCP Security Gateway:** Request and response interception for all MCP tool calls with PII/CRI detection, prompt injection blocking, and configurable response policies (BLOCK / SANITIZE / LOG)
*   **Policy Runtime Engine:** OPA/Rego-based policy evaluation at every agent action, supporting both built-in rules and custom enterprise policies
*   **Continuous Trust Scoring:** Dynamic 0-1000 trust score per agent that adapts based on behavior, with automatic capability revocation on threshold breach
*   **Cryptographic Agent Identity:** Ed25519 key pairs for agent signing, SPIFFE-compatible for service mesh environments
*   **Tamper-Evident Audit:** Hash-chain linked governance events that cannot be retroactively modified

#### 📚 Resources

*   📖 [AGT Integration Guide](https://github.com/Azure-Samples/ai-hub-gateway-solution-accelerator/blob/citadel-v1/guides/agent-governance-toolkit-integration.md): Step-by-step setup for Citadel deployers
*   🧪 [Citadel Governed Agent Example](https://github.com/microsoft/agent-governance-toolkit/tree/main/examples/citadel-governed-agent): Working example with mock mode for local testing
*   📚 [AGT Documentation](https://microsoft.github.io/agent-governance-toolkit): Full quickstart, tutorials, and API reference

> [!NOTE]
> AGT is an independent open-source project that extends the Citadel platform. It provides the in-process policy runtime engine for Layer 2, enabling comprehensive agent governance regardless of the selected agent framework or hosting environment.

***

## 🌟 Conclusion: The Strategic Value of Microsoft's Layered Approach

### 🔄 Transforming AI Governance from Constraint to Enabler

Microsoft's layered approach to AI security and governance represents a fundamental reimagining of how enterprises can scale AI innovation while maintaining trust, security, and compliance. By architecting governance as a unified, multi-layer system rather than a collection of disparate tools, Microsoft addresses the core challenge facing enterprises in 2026: the governance-velocity paradox.

### 🏅 Key Strategic Advantages

1.  🧩 Comprehensive Coverage Without Complexity  
    The four-layer architecture provides complete governance coverage while maintaining clear separation of concerns:

    *   Runtime enforcement (Layer 1) ensures every AI interaction is governed
    *   Observability and compliance (Layer 2) provide visibility and automated policy enforcement and ensure agents are executing as intended and compliant with regulations
    *   Agent identity (Layer 3) transforms agents into managed enterprise assets
    *   Security fabric (Layer 4) integrates protection across all layers

    This architecture enables organizations to implement sophisticated governance without overwhelming operational teams.

2.  🚀 Scale with Confidence  
    The layered approach is purpose-built for scale, enabling organizations to grow from 10 agents to 10,000 with consistent governance:
    *   Hub-and-spoke deployment allows local autonomy with central oversight
    *   Automated compliance eliminates manual bottlenecks
    *   Fleet operations provide visibility across entire agent ecosystem
    *   Reusable patterns accelerate deployment of new agents

3.  🏗️ Built on Microsoft’s AI Experience  
    Microsoft’s governance capabilities are informed by internal experience building, securing, and governing AI systems. Customers benefit from:
    *   Responsible AI Standards embedded in engineering processes
    *   Office of Responsible AI ensuring ethical AI development
    *   Transparency notes, fairness analysis, and explainability tools
    *   Proven patterns validated through Microsoft’s own AI deployments

4.  🏆 Industry Recognition and Market Leadership  
    The IDC MarketScape Leader designation validates Microsoft’s approach as best-in-class for unified AI governance. Key differentiators identified by IDC include:
    *   End-to-end governance spanning traditional ML, generative AI, and agentic AI
    *   Native integration across Foundry, Agent 365, Purview, Entra, and Defender
    *   Comprehensive approach removing disparate and disconnected tooling
    *   Operational maturity pairing technical controls with mature governance processes

### 🧱 The Trust Foundation for AI Transformation

Ultimately, Microsoft's layered approach provides the trust foundation necessary for AI transformation at enterprise scale. As the presentation emphasizes:

> **"💡 Those that can trust will scale. Those that scale AI effectively will win."**

The layered architecture enables this virtuous cycle:

*   ✅ **Governance enables trust** through comprehensive controls and visibility
*   ✅ **Trust enables scale** by removing barriers to AI adoption
*   ✅ **Scale delivers competitive advantage** through AI-driven innovation

### 🔮 Future-Proofing AI Governance

The layered approach is designed for adaptability as AI technology and regulations evolve:

*   🔌 **Protocol-agnostic:** Supports REST, MCP, A2A, and emerging protocols
*   ☁️ **Multi-cloud capable:** Consistent governance across hybrid and cloud environments
*   🧩 **Extensible:** Partner integrations (Credo AI, Saidot) enhance capabilities
*   📜 **Regulatory alignment:** With many layered controls in place, mapping regulatory requirements to technical controls becomes more straightforward, enabling faster compliance with new regulations as they arise.

### 📊 Measurable Business Impact

Organizations implementing Microsoft's layered governance approach can expect:

| Metric | Impact |
|--------|--------|
| 💰 Regulatory expenses | **20% reduction** through effective governance technologies |
| 🚀 GenAI pilot success | **95% improvement** vs. ungoverned approaches |
| 🛡️ Data breach risk from shadow AI | **80% reduction** |
| 🏆 AI governance effectiveness | **3.4x higher** |
| ⚡ Time-to-value | **Faster** with pre-built patterns and automation |

### 🚀 Call to Action for Enterprises

To capitalize on Microsoft's layered approach, enterprises should:

| Step | Action | Description |
|------|--------|-------------|
| **1** | 🔍 **Assess current state** | Evaluate existing AI governance gaps and risks |
| **2** | 🗓️ **Plan deployment** | Design hub-and-spoke architecture aligned with organizational structure |
| **3** | 🛠️ **Implement in phases** | Deploy governance hub, enable observability, activate agent identity |
| **4** | 🛡️ **Integrate security fabric** | Connect Defender, Purview, and Entra |
| **5** | 🎓 **Enable stakeholders** | Train governance teams, developers, and operators |
| **6** | 📊 **Measure and optimize** | Track compliance, costs, and time-to-value metrics |

> [!IMPORTANT]
> The era of AI at scale demands governance as a strategic capability, not a compliance burden. Microsoft's layered approach provides the architecture, tools, and ecosystem to make this vision a reality.

### 📚 Key Resources and References

*   📘 Citadel End-to-End Guidance: <https://aka.ms/foundry-citadel>
*   🏛️ Citadel Governance Hub (central deployment): <https://aka.ms/ai-hub-gateway>
*   🧱 Citadel Agents Environment (spoke deployments): <https://github.com/Azure/AI-Landing-Zones>
*   📚 Microsoft Learn – AI Gateway in Azure API Management: [learn.microsoft.com](https://learn.microsoft.com/en-us/azure/api-management/genai-gateway-capabilities)
*   📚 Microsoft Learn – Foundry Control Plane Overview: [learn.microsoft.com](https://learn.microsoft.com/en-us/azure/ai-foundry/control-plane/overview)
*   📚 Microsoft Learn – Governing Agent Identities with Entra ID: [learn.microsoft.com](https://learn.microsoft.com/en-us/entra/id-governance/agent-id-governance-overview)
*   📄 EU AI Act High-Risk Requirements Guide: [euairisk.com](https://euairisk.com/resources/eu-ai-act-high-risk-requirements)
*   🔓 Agent Governance Toolkit (open-source agent-level governance): [github.com/microsoft/agent-governance-toolkit](https://github.com/microsoft/agent-governance-toolkit)
***