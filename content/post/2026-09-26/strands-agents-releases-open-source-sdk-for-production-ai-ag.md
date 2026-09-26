---
title: "Strands Agents Releases Open-Source SDK for Production AI Agents"
slug: "strands-agents-releases-open-source-sdk-for-production-ai-agents"
description: "Strands Agents has released an open-source SDK for building and running production AI agents in Python and TypeScript. The SDK allows developers to build an agent harness and control it end-to-end..."
date: 2026-09-26T22:01:53+05:30
tags: [OpenSource, AIAgents, Python, TypeScript, SDK]
categories: ["AI", "AI Agents", "Software Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/209155962?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Strands Agents Releases Open-Source SDK for Production AI Agents

Strands Agents has released an open-source SDK for building and running production AI agents in Python and TypeScript. The SDK allows developers to build an agent harness and control it end-to-end across any model and any cloud.

## 🔍 Overview
Strands Agents provides a model-driven approach to building AI agents in a few lines of code. It is designed for developers who would otherwise write their own agent loop, as it runs within the user's process with no hosted control plane.

## ⚙️ Key Details
The SDK includes a variety of built-in capabilities for agent management and observability:

* **Lifecycle Controls:** Token budgets, turn limits, stop reasons, and cancellation.
* **Agent Capabilities:** Structured output, tools, and MCP.
* **Architecture Patterns:** Memory, sessions, and multi-agent patterns.
* **Operations:** Streaming, guardrails, tracing, and evals.
* **Model Portability:** Ability to swap backends when scaling while keeping code the same.

## 🧩 How it works
The project is maintained as a monorepo containing the following components:

| Component | Description | Access/Platform |
| :--- | :--- | :--- |
| Python Strands harness | Fully assembled agent via `create_harness()` | PyPI |
| TypeScript Strands harness | Fully assembled agent via `createHarness()` | npm |
| `strands` CLI | Prototype and chat with a harness agent from the terminal | npm |
| Python SDK | Agent loop, model providers, and tools | PyPI |
| TypeScript SDK | Agent loop, model providers, and tools | npm |

## 💡 Why it matters
The SDK is model agnostic, providing first-class support for Gemini, OpenAI, Anthropic, and Amazon Bedrock, as well as custom providers. It provides context management, execution limits, and observability built in before any configuration is written, and the agent loop traces every decision.

#OpenSource #AIAgents #Python #TypeScript #SDK

---

*Source: [strands-agents/harness-sdk](https://github.com/strands-agents/harness-sdk)*
