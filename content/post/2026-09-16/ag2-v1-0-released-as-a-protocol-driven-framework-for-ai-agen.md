---
title: "AG2 v1.0 Released as a Protocol-Driven Framework for AI Agents"
slug: "ag2-v1-0-released-as-a-protocol-driven-framework-for-ai-agents"
description: "AG2 (formerly AutoGen) has released v1.0, transitioning to a protocol-driven framework designed to streamline the development and research of agentic AI."
date: 2026-09-17T00:45:10+05:30
tags: [AG2, AutoGen, AIagents, OpenSource]
categories: ["AI", "AI Agents", "Software Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/188122941?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AG2 v1.0 Released as a Protocol-Driven Framework for AI Agents

AG2 (formerly AutoGen) has released v1.0, transitioning to a protocol-driven framework designed to streamline the development and research of agentic AI.

## 🔍 Overview
AG2 is an open-source programming framework used for building AI agents and facilitating cooperation among multiple agents to solve tasks. The project is currently maintained by a dynamic group of volunteers from several organizations.

## 🧩 How it works
AG2 offers several core capabilities for agentic AI:
* Support for various large language models (LLMs) and tool use.
* Agents capable of interacting with each other.
* Autonomous and human-in-the-loop workflows.
* Multi-agent conversation patterns.

## ⚙️ Key details
With the release of v1.0, the project has split into two distinct distributions. AG2 v1.0 is not a drop-in upgrade from Classic, as the imports, orchestration, and agent model have changed.

| Feature | AG2 | AG2 Classic |
| :--- | :--- | :--- |
| **Repository** | ag2ai/ag2 | ag2ai/ag2-classic |
| **Documentation** | docs.ag2.ai | classic.docs.ag2.ai |
| **Import Name** | `import ag2` | `import autogen` |
| **Core Agent** | `Agent` | `ConversableAgent` |
| **Multi-Agent Feature** | Network (hub + channels) | `GroupChat`, swarms, nested chats |
| **Install Command** | `pip install ag2` | `pip install ag2-classic` |

## 🚀 Availability
AG2 Classic remains maintained and installable for those with existing code; users can pin the classic distribution instead of `ag2>=1.0` to keep existing code working. For those interested in becoming a maintainer, project administrators Chi Wang and Qingyun Wu can be contacted via support@ag2.ai.

#AG2 #AutoGen #AIagents #OpenSource

---

*Source: [ag2ai/ag2](https://github.com/ag2ai/ag2)*
