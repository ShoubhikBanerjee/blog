---
title: "Persistent Memory Tool agentmemory Launches for AI Coding Agents"
slug: "persistent-memory-tool-agentmemory-launches-for-ai-coding-agents"
description: "The agentmemory implementation has been released to provide persistent memory for coding agents, ensuring they remember historical context across sessions and eliminating the need for constant..."
date: 2026-09-14T18:04:24+05:30
tags: [AICoding, LLM, agentmemory, DeveloperTools, AIagents]
categories: ["AI", "Software Development", "Artificial Intelligence", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/48523873?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Persistent Memory Tool agentmemory Launches for AI Coding Agents

The agentmemory implementation has been released to provide persistent memory for coding agents, ensuring they remember historical context across sessions and eliminating the need for constant re-explaining.

## 🔍 Overview
This project serves as an implementation that extends Andrej Karpathy's LLM Wiki pattern. It enhances the original concept by adding several built-in capabilities:

* Confidence scoring
* Lifecycle management
* Knowledge graphs
* Hybrid search

## ⚙️ Key Details

### Supported Agents and Clients
The tool provides persistent memory for a wide variety of coding tools and Model Context Protocol (MCP) clients, including:
* Claude Code
* GitHub Copilot CLI
* Cursor
* Gemini CLI
* Codex CLI
* Hermes
* OpenClaw
* pi
* OpenCode
* Any MCP client

### Configuration and Search Modes
How the system recalls memory depends heavily on your search configuration and provider settings:

| Search Method | Description |
|---|---|
| `memory_recall` | Utilizes BM25 (representing the `mem::search` path). |
| `memory_smart_search` | Fuses structural graph matches when graph data already exists. |

* **Keyless Mode:** Operating in keyless mode completely disables vector embeddings.
* **On-Device Semantic Recall:** To enable free, on-device semantic recall, you can set `EMBEDDING_PROVIDER=local` inside your `~/.agentmemory/.env` file and restart. Upon the first embedding request, the system automatically downloads `Xenova/all-MiniLM-L6-v2`. Subsequent inference runs entirely locally on your device.
* **Observation Compression:** While selecting an LLM provider enables general LLM capabilities, actual LLM-written observation compression only starts if you set the environment variable `AGENTMEMORY_AUTO_COMPRESS=true`.

## 🚀 Installation and Setup

### System Requirements
Installation requirements differ depending on your operating system environment:

* **macOS and Linux:** The automatic installation of the iii-engine requires `curl`, a POSIX `sh`, and `tar`. Note that minimal Docker images, such as `node:20-slim`, may lack these packages.
* **Windows:** Native Windows installations require you to manually install the pinned iii-engine v0.11.2 executable (`iii.exe`). Alternatively, you can use WSL2 or Docker Desktop as supported setup paths.

### Initialization and First Run
To initialize the setup, you can use npx. Incorporating the `-y` flag automatically accepts npx's package prompt, while using `@latest` ensures you do not run a stale cached release.

On its first run, `agentmemory` launches an interactive setup that guides you through the following configurations:
1. Choosing which agents to wire (such as Claude Code, Cursor, Codex, Gemini CLI, or OpenCode).
2. Selecting an LLM provider or opting to remain keyless.
3. Seeding the initial configuration.
4. Launching the memory server and starting its pinned iii-engine.
5. Offering to install the tool globally so that the basic `agentmemory` command can be executed from any location.

#AICoding #LLM #agentmemory #DeveloperTools #AIagents

---

*Source: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)*
