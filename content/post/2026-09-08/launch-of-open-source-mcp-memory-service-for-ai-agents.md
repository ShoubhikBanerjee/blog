---
title: "Launch of Open-Source MCP Memory Service for AI Agents"
description: "A new open-source memory backend for AI agents has been released, providing a self-hosted service for storing decisions and sharing causal knowledge graphs."
date: 2026-09-09T00:16:34+05:30
tags: [OpenSource, AIagents, MCP, KnowledgeGraph]
categories: ["AI Agents", "Open Source Software", "Software Development"]
image: "https://avatars.githubusercontent.com/u/5000709?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Launch of Open-Source MCP Memory Service for AI Agents

A new open-source memory backend for AI agents has been released, providing a self-hosted service for storing decisions and sharing causal knowledge graphs.

## 🔍 Overview
The MCP Memory Service allows agents to capture project context, architecture decisions, and code patterns automatically. This ensures new sessions begin with existing knowledge. The service is framework-agnostic and compatible with several tools, including:

* LangGraph
* CrewAI
* AutoGen
* Claude Desktop
* OpenCode
* Any HTTP client

## 🧩 How it works
The system utilizes a knowledge graph with typed edges to track causes, fixes, and contradictions, allowing agents to share causal chains rather than just facts. Technical specifications include:

* **Local Embeddings**: Run via ONNX to ensure memory stays within the user's infrastructure.
* **Performance**: Context retrieval occurs in 5ms.
* **Consolidation**: Autonomous consolidation compresses old memories.
* **Real-time Updates**: SSE events provide notifications when memories are stored or deleted.

## ⚙️ Key details
The service is licensed under Apache 2.0 and features a REST API with 76 endpoints. Key API and configuration elements include:

| Feature | Description |
| :--- | :--- |
| X-Agent-ID header | Auto-tags memories by agent identity for scoped retrieval |
| conversation_id | Bypasses deduplication for incremental conversation storage |
| REST API | Runs at http://localhost:8000 without requiring an MCP client library |
| Interface | Includes a CLI, dashboard, REST API, MCP, and OAuth |

## 🚀 Availability
Users can install the service via `pip install mcp-memory-service`. Configuration paths for Claude Desktop are provided for multiple operating systems:

* **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
* **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
* **Linux**: `~/.config/Claude/claude_desktop_config.json`

Command-line options include `claude mcp add memory -- memory server` and `MCP_ALLOW_ANONYMOUS_ACCESS=true memory server --http`.

## 💡 Why it matters
Because the service is self-hosted, it incurs zero cloud cost and avoids cloud lock-in and API costs. Memory is shared across all agents and runs.

#OpenSource #AIagents #MCP #KnowledgeGraph

---

*Source: [doobidoo/mcp-memory-service](https://github.com/doobidoo/mcp-memory-service)*
