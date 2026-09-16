---
title: "OpenAI deprecates AgentKit as AI agent platform market consolidates"
slug: "openai-deprecates-agentkit-as-ai-agent-platform-market-consolidates"
description: "On 3 June 2026 OpenAI announced the deprecation of its visual Agent Builder (AgentKit) and its managed Evals platform, signalling a rapid shift in the AI‑agent tooling landscape."
date: 2026-09-16T22:05:42+05:30
tags: [OpenAI, AIAgents, AgentPlatforms]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Enterprise Software", "Machine Learning"]
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI deprecates AgentKit as AI agent platform market consolidates

On 3 June 2026 OpenAI announced the deprecation of its visual Agent Builder (AgentKit) and its managed Evals platform, signalling a rapid shift in the AI‑agent tooling landscape.

## 🔍 Overview
- AgentKit launched in October 2025 and was retired on 3 June 2026 with a shutdown deadline of 30 Nov 2026. Users are directed back to the Agents SDK.
- The same notice retired OpenAI’s Evals platform and recommended the open‑source Promptfoo tool.
- OpenAI’s Assistants API shut down on 26 Aug 2026; the Responses API is the migration path.
- Microsoft discontinued AutoGen and Semantic Kernel on 3 April 2026 to release a unified Agent Framework 1.0.
- Google retired the Vertex AI brand on 22 Apr 2026, folding all services into the Gemini Enterprise Agent Platform.

## 🧩 Architecture Layers
AI‑agent development platforms consist of four distinct layers:
1. **Agent harness** – infrastructure that wraps a model to manage long‑running tasks, acting as an operating system between model and application.
2. **Managed runtime** – the environment that hosts and scales the agent.
3. **Orchestration framework** – coordinates tool calls and workflow logic; the recommended starting point for self‑hosted infra.
4. **Control plane** – provides governance, monitoring, and lifecycle management.
- Two of these categories did not exist in mid‑2025; all four hyperscalers plus LangChain now ship a harness, a capability unavailable a year earlier.

## 📊 Market Realities
- Only **16 %** of enterprise agent deployments are true agents (model plans + executes) (Menlo Ventures, Dec 2025).
- The remaining 84 % are essentially routing logic with better branding, a phenomenon Gartner called **agent washing** in June 2025.
- 89 % of teams grant agents write permissions (up from 52 % a year earlier).
- Only **52.4 %** of teams run offline evaluations; this gap, not tool choice, stalls agent projects.

## 🛠️ Tool Landscape
| Product / Service | Deprecation / Change | Note |
|---|---|---|
| AgentKit (visual canvas) | 3 Jun 2026 (shutdown 30 Nov 2026) | Switch back to Agents SDK |
| OpenAI Evals platform | 3 Jun 2026 | Use Promptfoo (open source) |
| Assistants API | 26 Aug 2026 | Migrate to Responses API |
| AutoGen & Semantic Kernel | 3 Apr 2026 | Replaced by Agent Framework 1.0 |
| Vertex AI brand | 22 Apr 2026 | Integrated into Gemini Enterprise Agent Platform |

### Evaluation & Observability Vendors Acquired
| Vendor | Acquisition period |
|---|---|
| Weights & Biases | Within 16 months |
| Galileo | Within 16 months |
| Arize | Within 16 months |
- These acquisitions raise procurement questions about vendor longevity (e.g., “will this vendor exist in eighteen months”).

## 💡 Why it matters
- The market is consolidating around four functional layers rather than a single “agent platform”.
- Choosing a platform before understanding the layer needs can lock teams into costly rewrites.
- Evaluation and observability cut across all layers, yet many teams lack proper offline testing, contributing to project delays.
- Agent washing inflates vendor counts; Gartner estimates only ~130 of thousands of claimed agents are genuine.
- Open‑source options in the orchestration layer remain reversible, unlike proprietary runtime choices.


#OpenAI #AIAgents #AgentPlatforms

---

*Source: [Best AI agent development platforms and tools in 2026](https://www.pixelmatters.com/insights/ai-agent-development-platforms)*
