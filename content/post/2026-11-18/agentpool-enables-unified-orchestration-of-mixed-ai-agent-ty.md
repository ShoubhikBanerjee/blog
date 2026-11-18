---
title: "AgentPool enables unified orchestration of mixed AI agent types"
slug: "agentpool-enables-unified-orchestration-of-mixed-ai-agent-types"
description: "AgentPool is a unified agent orchestration hub that allows developers to configure and manage multiple AI agents, including native, ACP, AGUI, and Claude Code types, via YAML configuration. It..."
date: 2026-11-18T12:19:35+05:30
tags: [AIagents, AgentOrchestration, DeveloperTools, ACP]
categories: ["AI", "AI Agents", "Developer Tools", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/110931?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AgentPool enables unified orchestration of mixed AI agent types

AgentPool is a unified agent orchestration hub that allows developers to configure and manage multiple AI agents, including native, ACP, AGUI, and Claude Code types, via YAML configuration. It exposes these agents through standardized protocols such as ACP and OpenCode Server, enabling them to cooperate, delegate tasks, and communicate through a single interface.

## 🧩 How it works
AgentPool acts as a protocol bridge that centralizes agent definition. Users define all agents in a single YAML file, which supports:
- Native agents based on PydanticAI.
- Direct integrations like Claude Code and Codex.
- External ACP agents, such as Goose.
- AG-UI agents.

Once defined, agents can be organized into teams for parallel execution or chains for sequential processing. A coordinator agent can delegate work to any of the defined agents through the same unified interface.

## ⚙️ Key details
The system is fully configurable, allowing users to define models, tools, connections, triggers, and storage settings. AgentPool exposes agents through multiple server protocols:

| Protocol | Primary Use Case |
| :--- | :--- |
| ACP Server | IDE integration, real-time tool confirmations, and session management |
| OpenCode Server | Enables OpenCode TUI to control agents, including those on remote environments like Docker, SSH, and cloud sandboxes |

Installation and usage are handled via command-line tools:
- `uv tool install agentpool`
- `agentpool run assistant "Hello!"`
- `agentpool serve-acp agents.yml`

## 💡 Why it matters
The core capability of AgentPool is mixing different agent types within a single ecosystem. This allows for workflows where specific agents handle distinct tasks—such as using Claude Code for refactoring, Codex for advanced reasoning code editing, and custom agents for analysis—while maintaining a standardized communication layer.

#AIagents #AgentOrchestration #DeveloperTools #ACP

---

*Source: [phil65/agentpool](https://github.com/phil65/agentpool)*
