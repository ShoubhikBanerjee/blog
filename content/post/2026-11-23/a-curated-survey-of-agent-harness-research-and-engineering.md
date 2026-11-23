---
title: "A Curated Survey of Agent Harness Research and Engineering"
slug: "a-curated-survey-of-agent-harness-research-and-engineering"
description: "A curated, multiply-verified survey of **agent harness** research and engineering — the right level of abstraction for understanding the current frontier of LLM agents."
date: 2026-11-23T18:10:50+05:30
tags: [AIagents, MachineLearning, OpenSource, SoftwareDevelopment]
categories: ["AI", "Artificial Intelligence", "Software Development", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/128061718?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# A Curated Survey of Agent Harness Research and Engineering

A curated, multiply-verified survey of **agent harness** research and engineering — the right level of abstraction for understanding the current frontier of LLM agents.

## 🔍 Overview
- Total: 213 papers · 68 production harnesses / essays / talks · last updated 2026-10-26
- 116 papers + Claude Code / Codex / Cursor / OpenHands tools + Anthropic / OpenAI / Karpathy essays.
- Agent = Model + Harness.

## 🧩 How it works
- The harness is the layer *around* the model that turns it into an agent — the agent loop plus tools, memory, context, runtime, and safety.
- You can also define an agent as: **agent = model + harness**. The harness is the scaffolding around the model that connects it to the real world.
- This post focuses on the **Codex harness**, which provides the **core agent loop and execution logic** that underlies all Codex experiences and is surfaced through the Codex CLI.
- Agents can handle sophisticated tasks, but their implementation is often straightforward. They are typically just **LLMs using tools based on environmental feedback in a loop**.
- The agent loop is therefore a *component* of the harness — its core execution mechanism — not a peer of it.

## ⚙️ Key details
| Agent / Framework | Creator / Org | Description | Stars / Metrics |
| --- | --- | --- | --- |
| Continue | Continue | Continue — open-source AI coding agent as a VS Code / JetBrains extension, fully local-model friendly. | ~34.6k stars |
| AutoGen | Microsoft Research | AutoGen — programming framework for building multi-agent conversational systems. | ~59.4k stars |
| Aider | Paul Gauthier | Aider — AI pair programming in the terminal, git-aware by design. | ~47k stars (canonical org: Aider-AI/aider) |
| OpenHands | All-Hands-AI | OpenHands (formerly OpenDevin) — open-source platform for autonomous software development with browser, terminal, and co | Not specified |
| SWE-agent | Princeton NLP / SWE-agent | SWE-agent — agent-computer-interface (ACI) framework that takes a GitHub issue and autonomously fixes it with any LM. | ~1 |
| Goose | Block (fka Square) | Goose — Block's open-source, extensible AI agent that goes beyond code suggestions to install, execute, edit, and test c | Not specified |
| Cline | Cline | Cline (formerly Claude Dev) — autonomous coding agent shipped as VS Code extension, SDK, and CLI. | ~64k stars |
| CrewAI | CrewAI | CrewAI — framework for orchestrating role-playing, collaborative autonomous AI agents (crew, task, tool). | ~54.8k stars |

#AIagents #MachineLearning #OpenSource #SoftwareDevelopment

---

*Source: [NeuraLiying/Awesome-Agent-Harnesses](https://github.com/NeuraLiying/Awesome-Agent-Harnesses)*
