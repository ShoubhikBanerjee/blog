---
title: "Context Engine launches AI skills for semantic code search and memory"
slug: "context-engine-launches-ai-skills-for-semantic-code-search-and-memory"
description: "Context Engine has launched a suite of AI agent skills designed to teach coding assistants how to utilize 30+ MCP tools for semantic search, symbol graph navigation, and memory. The tool provides..."
date: 2026-11-19T12:23:35+05:30
tags: [AI, CodingAssistants, MCP, SemanticSearch, DeveloperTools]
categories: ["AI", "AI Agents", "Developer Tools", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/256224968?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Context Engine launches AI skills for semantic code search and memory

## 🆕 Overview
Context Engine has launched a suite of AI agent skills designed to teach coding assistants how to utilize 30+ MCP tools for semantic search, symbol graph navigation, and memory. The tool provides semantic code search, memory, and symbol intelligence specifically for AI coding assistants.

## 🧩 How it works
The Context Engine MCP server indexes workspaces, allowing agents to call `repo_search` first for any question about the codebase before using standard commands like `ls`, `find`, `Grep`, or `Read`. Results from `repo_search` are verified source with exact line ranges, which agents are instructed to treat as already read.

The system includes specific tools for different coding tasks:
*   `repo_search`: Finds code by behavior, concept, error text, or identifier; supports multiple queries and narrowing by language, path, or type.
*   `context_answer`: Explains how or why something works across several files with citations.
*   `symbol_graph`: Shows definitions, callers, callees, importers, and references for specific symbols.
*   `graph_query`: Performs multi-hop impact analysis before making changes.
*   `cross_repo_search`: Identifies code that may exist in other indexed repositories.

For safety and efficiency, the system recommends fetching every involved symbol in one call before editing. For renames or signature changes, `symbol_graph` with `query_type=references` is used to get every site.

## ⚙️ Key details
The tool supports various development environments through specific installation and configuration methods:
*   **Claude Code & Codex**: Recommends pasting guidance into `CLAUDE.md` or `AGENTS.md` to reach subagents. Codex can install natively using its built-in skill installer, which pulls `.codex/skills/context-engine/` into `~/.codex/skills/` automatically.
*   **Cursor**: Rules are included in `.cursorrules` at the workspace root, which Cursor picks up automatically if the file is present.
*   **Terminal-based MCP clients**: An MCP bridge allows connection without VS Code for clients like Claude Code or Codex.
*   **Daemon Management**: The system runs as a background daemon with a default file watch interval of 30 seconds. Users can authenticate, index codebases, and monitor changes. The daemon and MCP server share authentication via `~/.ctxce/auth.json`, and logs are stored at `~/.context-engine/daemon.log`.
*   **Installation**: Native installation is available from the public GitHub repo, which pulls the skill and auto-loads MCP tool guidance into the session.

## 🚀 Availability
Users can get a free account at dev.context-engine.ai.

#AI #CodingAssistants #MCP #SemanticSearch #DeveloperTools

---

*Source: [Context-Engine-AI/Context-Engine](https://github.com/Context-Engine-AI/Context-Engine)*
