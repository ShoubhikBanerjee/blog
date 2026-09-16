---
title: "mcp-memory-service Released as Open-Source Memory Backend for AI Agents"
slug: "mcp-memory-service-released-as-open-source-memory-backend-for-ai-agents"
description: "A new open-source memory backend for AI agents, mcp-memory-service, has been released to allow agents to store decisions and share causal knowledge graphs without cloud lock-in or API costs."
date: 2026-09-17T00:50:10+05:30
tags: [MCP, AIagents, OpenSource, KnowledgeGraph]
categories: ["AI", "AI Agents", "Software Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/5000709?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# mcp-memory-service Released as Open-Source Memory Backend for AI Agents

A new open-source memory backend for AI agents, mcp-memory-service, has been released to allow agents to store decisions and share causal knowledge graphs without cloud lock-in or API costs.

## 🔍 Overview
mcp-memory-service is a self-hosted service that provides a memory backend via REST API, MCP, OAuth, a CLI, and a dashboard. It is licensed under Apache 2.0 and supports integration with various frameworks and clients, including:

* LangGraph
* CrewAI
* AutoGen
* Claude Desktop
* OpenCode
* Any HTTP client

## 🧩 How it works
The service utilizes a knowledge graph with typed edges to track causes, fixes, and contradictions, allowing agents to share causal chains rather than just facts. 

Key technical mechanisms include:
* **Local Embeddings**: Embeddings run locally via ONNX to ensure memory remains within the user's infrastructure.
* **Autonomous Consolidation**: Old memories are compressed through autonomous consolidation.
* **Scoped Retrieval**: The `X-Agent-ID` header automatically tags memories by agent identity.
* **Incremental Storage**: The `conversation_id` allows users to bypass deduplication for incremental conversation storage.
* **Real-time Updates**: SSE events provide notifications when any agent stores or deletes a memory.

## ⚙️ Key details

| Feature | Specification |
| :--- | :--- |
| Retrieval Speed | 5ms |
| REST API | Framework-agnostic with 76 endpoints |
| Deployment | Self-hosted, zero cloud cost |

## 🚀 Availability
The project is available on GitHub at https://github.com/doobidoo/mcp-memory-service as of 5 September 2026. 

**Installation and Setup:**
* **Installation**: `pip install mcp-memory-service`
* **Local Execution**: `MCP_ALLOW_ANONYMOUS_ACCESS=true memory server --http` (runs REST API at http://localhost:8000)
* **Claude Desktop Integration**: Add to config files located at `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS), `%APPDATA%\Claude\claude_desktop_config.json` (Windows), or `~/.config/Claude/claude_desktop_config.json` (Linux), or use the command `claude mcp add memory -- memory server`.

#MCP #AIagents #OpenSource #KnowledgeGraph

---

*Source: [doobidoo/mcp-memory-service](https://github.com/doobidoo/mcp-memory-service)*
