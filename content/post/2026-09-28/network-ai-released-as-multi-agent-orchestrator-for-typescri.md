---
title: "Network-AI Released as Multi-Agent Orchestrator for TypeScript and Node.js"
slug: "network-ai-released-as-multi-agent-orchestrator-for-typescript-and-node-js"
description: "Network-AI is a TypeScript/Node.js multi-agent orchestrator designed to add coordination, guardrails, and governance to AI agent stacks. It is currently available as release v5.15.3 with 3679 passing..."
date: 2026-09-28T22:02:06+05:30
tags: [TypeScript, Nodejs, AIagents, MultiAgentSystems, Orchestration]
categories: ["AI", "AI Agents", "Software Development", "AI Governance"]
image: "https://avatars.githubusercontent.com/u/120467681?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Network-AI Released as Multi-Agent Orchestrator for TypeScript and Node.js

Network-AI is a TypeScript/Node.js multi-agent orchestrator designed to add coordination, guardrails, and governance to AI agent stacks. It is currently available as release v5.15.3 with 3679 passing tests.

## 🔍 Overview
Network-AI provides a framework for managing parallel agents through several core governance and coordination mechanisms:

* **Shared Blackboard:** Uses a locking mechanism with an atomic `propose → validate → commit` mutex to prevent race conditions and split-brain failures before writes reach shared state.
* **Guardrails and Budgets:** Includes FSM governance, per-agent token ceilings, permission gating, and HMAC / Ed25519 audit trails.
* **GovernedModelGateway:** Manages a chain of model refusal, cross-model fallback, fallback-credit repricing, effort governance, and thinking-block handoff within a single audited and budgeted call.

## 🧩 How it works
Network-AI utilizes specific tools and managers to handle agent context and state:

| Feature | Function |
| :--- | :--- |
| `ContextComposer` | Assembles relevance-ranked, token-budgeted context packs using semantic/lexical data, recency decay, scope affinity, and position-aware layout. |
| `context_manager.py` | Injects goals, decisions, stack, milestones, and banned patterns into every system prompt. |
| MCP Tools | `context_pack` and `blackboard_search` allow agents to pull curated state instead of the full blackboard. |

## ⚙️ Key details
**v5.0 Modules**
The orchestrator includes a variety of modules:
* Agent VCR (record/replay)
* Comparison runner and coverage reporter
* Goal DSL and approval inbox
* Job queue and gRPC/HTTP transport
* Playground REPL and adapter test harness

**Supported Adapters**
Network-AI includes 32 adapters, including:
* LangChain (+ streaming), AutoGen, CrewAI, LlamaIndex, and Semantic Kernel
* OpenAI Assistants, OpenAI Responses, and OpenAI Agents SDK
* Anthropic Computer Use and Claude Agent SDK
* Vertex AI, Gemini (Developer API), and Pydantic AI
* Haystack, DSPy, Agno, MCP, and LangGraph
* Browser Agent, OpenClaw, A2A, Codex, MiniMax, NemoClaw, APS, Copilot, and RLM
* Hermes (NousResearch Hermes / any OpenAI-compatible endpoint)
* Orchestrator (hierarchical multi-orchestrator) and Custom (+ streaming)

## 🚀 Availability
**System Requirements**
* Node.js >=18.0.0
* TypeScript 6.x

**Deployment Options**
* **TypeScript/Node.js library:** `import { createSwarmOrchestrator } from 'network-ai'`
* **MCP server:** `npx network-ai-server --port 3001`
* **CLI:** `network-ai bb get status` or `network-ai audit tail`
* **Claude Code plugin:** `/plugin install network-ai@network-ai`
* **Gemini CLI extension:** `gemini extensions install https://github.com/Jovancoding/Network-AI`
* **OpenClaw skill:** `clawhub install network-ai`

#TypeScript #Nodejs #AIagents #MultiAgentSystems #Orchestration

---

*Source: [Jovancoding/Network-AI](https://github.com/Jovancoding/Network-AI)*
