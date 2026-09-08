---
title: "AG2 v1.0 Releases Protocol-Driven Framework and Splits from AutoGen Classic"
description: "AG2 (formerly AutoGen) has updated its development structure, introducing a protocol-driven framework as the top-level package in v1.0 while moving the original AutoGen-derived framework to a..."
date: 2026-09-09T00:16:34+05:30
tags: [AG2, AutoGen, AIagents, OpenSource]
categories: ["AI Agents", "Software Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/188122941?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AG2 v1.0 Releases Protocol-Driven Framework and Splits from AutoGen Classic

AG2 (formerly AutoGen) has updated its development structure, introducing a protocol-driven framework as the top-level package in v1.0 while moving the original AutoGen-derived framework to a separate repository known as AG2 Classic.

## 🔍 Overview
AG2 is an open-source programming framework designed to streamline the research and development of agentic AI. It facilitates the building of AI agents and cooperation among multiple agents to solve tasks. Key features include:

* Agents capable of interacting with each other
* Support for tool use and various large language models (LLMs)
* Multi-agent conversation patterns
* Autonomous and human-in-the-loop workflows

## ⚙️ Key details
AG2 v1.0 is not a drop-in upgrade from Classic, as the agent model, orchestration, and imports have changed. The project is currently maintained by a dynamic group of volunteers from several organizations.

| Feature | AG2 Classic | AG2 v1.0 |
| :--- | :--- | :--- |
| Repository | ag2ai/ag2-classic | ag2ai/ag2 |
| Documentation | classic.docs.ag2.ai | docs.ag2.ai |
| Import | `import autogen` | `import ag2` |
| Core agent | `ConversableAgent` | `Agent` |
| Multi-agent | `GroupChat`, swarms, nested chats | Network (hub + channels) |

## 🚀 Availability
Users of the original framework can continue using AG2 Classic, which remains maintained and installable. To ensure existing code keeps working, users should pin the classic distribution using `pip install ag2-classic` instead of `ag2>=1.0`.

The new protocol-driven framework is available via `pip install ag2`. To get started, users can set up their API keys and run their first agent.

#AG2 #AutoGen #AIagents #OpenSource

---

*Source: [ag2ai/ag2](https://github.com/ag2ai/ag2)*
