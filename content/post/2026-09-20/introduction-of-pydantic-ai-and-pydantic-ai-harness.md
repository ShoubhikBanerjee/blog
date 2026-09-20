---
title: "Introduction of Pydantic AI and Pydantic AI Harness"
slug: "introduction-of-pydantic-ai-and-pydantic-ai-harness"
description: "Pydantic AI has been released as a Python AI SDK providing a typed, extensible agent loop where models can be changed via a string swap."
date: 2026-09-20T22:01:28+05:30
tags: [PydanticAI, Python, AIAgents, LLM, SDK]
categories: ["AI", "AI Agents", "Software Development", "Python"]
image: "https://avatars.githubusercontent.com/u/110818415?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Introduction of Pydantic AI and Pydantic AI Harness

Pydantic AI has been released as a Python AI SDK providing a typed, extensible agent loop where models can be changed via a string swap.

## 🔍 Overview
The SDK allows the same agent to run across various environments, including:
* Web frontends
* Terminals
* Voice calls
* Durable background queues
* GitHub Actions
* As a plain object called via `run()`

## 🧩 How it works

| Component | Function |
| :--- | :--- |
| Pydantic AI | Python AI SDK for typed data extraction and agent loops |
| Pydantic AI Harness | Provides capabilities for complex, long-running work including memory, guardrails, planning, and storage |
| Pydantic Graph | Separate package for typed control flow |
| Pydantic Evals | Separate package for testing agent behavior similar to pytest |
| Pydantic Logfire | AI observability platform for the entire app |
| Pydantic AI Gateway | Model key management with real-time cost monitoring and budget control |
| genai-prices | Maintains current model pricing |
| Monty | Sandboxed Python interpreter for running model-written code |

## ⚙️ Key details
* **Capabilities:** Pydantic AI includes image generation and embeddings. Pydantic AI Harness can be used to build a complete coding agent featuring workspace-rooted file access, an allowlisted shell, repo orientation, and context management for long sessions.
* **Integration:** The Gateway supports self-hosting and uses plain OpenTelemetry instrumentation, ensuring compatibility with existing backends.
* **Scope:** The system supports a range of use cases from simple typed data extraction to complex multi-agent collaboration.

#PydanticAI #Python #AIAgents #LLM #SDK

---

*Source: [pydantic/pydantic-ai](https://github.com/pydantic/pydantic-ai)*
