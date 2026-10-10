---
title: "Microsoft Agent Framework succeeds AutoGen as repository enters maintenance mode"
slug: "microsoft-agent-framework-succeeds-autogen-as-repository-enters-maintenance-mode"
description: "AutoGen's repository has officially transitioned into maintenance mode, receiving no new features or enhancements as it moves to a community-managed model. Microsoft is directing new users to the..."
date: 2026-10-10T22:05:31+05:30
tags: [Microsoft, AutoGen, AIAgents, Python, SoftwareDevelopment]
categories: ["AI", "AI Agents", "Software Development", "Machine Learning"]
image: "https://images.unsplash.com/photo-1677442136019-21780ecad995?w=1200&h=630&fit=crop"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft Agent Framework succeeds AutoGen as repository enters maintenance mode

AutoGen's repository has officially transitioned into maintenance mode, receiving no new features or enhancements as it moves to a community-managed model. Microsoft is directing new users to the Microsoft Agent Framework, a .NET and Python framework for agents and multi-agent workflows, and has provided a migration guide for current AutoGen users.

## 🧩 How it works

AutoGen enables the creation of agents that interact within a shared conversation. This framework is built for asynchronous operation, utilizing an AgentChat API where developers write `async def` functions and execute them with `asyncio.run`. To avoid resource leaks, developers must ensure they call `await model_client.close()` to release LLM connections.

A typical implementation might involve a writer drafting content and a critic responding to the draft. In this setup, the critic views the draft cold, with no investment in defending the work, and the loop continues until a termination condition is triggered.

## ⚙️ Key details

Termination conditions are the primary safety feature for agent teams, preventing agents from infinitely exchanging messages and incurring unnecessary costs. The framework allows developers to join conditions using the `|` operator, stopping the run as soon as any single condition fires.

| Termination Condition | Description |
| :--- | :--- |
| `TextMentionTermination("APPROVE")` | Ends the run when a message contains the specific trigger word. |
| `MaxMessageTermination` | Acts as a hard cap on the total number of messages in a run. |
| External Termination | An object that can be fired from your application to stop the team. |

## 🚀 Availability

To use the framework, Python 3.10 or later is required. While examples typically utilize the OpenAI API via the `OPENAI_API_KEY` environment variable, other providers are supported through specific client classes in extension packages. Agents also gain increased utility through the integration of tools.

Developers can execute agent teams in two ways:
* `await team.run(task=...)`: Returns a `TaskResult` including a stop reason once the team concludes.
* `team.run_stream(task=...)`: Yields messages as they arrive, which can be printed using `Console` during development.

Teams maintain their state between runs. To prevent old context from leaking into new tasks, developers should call `await team.reset()` before reuse.

#Microsoft #AutoGen #AIAgents #Python #SoftwareDevelopment

---

*Source: [AutoGen Tutorial: Multi-Agent Conversations with Microsoft's Framework | Sam Austin AI](https://samaustinai.com/autogen-tutorial-multi-agent-conversations-microsoft)*
