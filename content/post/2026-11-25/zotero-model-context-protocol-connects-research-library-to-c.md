---
title: "Zotero Model Context Protocol Connects Research Library to Claude, ChatGPT and More"
slug: "zotero-model-context-protocol-connects-research-library-to-claude-chatgpt-and-more"
description: "Zotero has released the Model Context Protocol (MCP) integration, allowing its research library to be accessed directly from AI assistants such as Claude and ChatGPT."
date: 2026-11-25T18:07:47+05:30
tags: [Zotero, AIIntegration, ModelContextProtocol]
categories: ["AI", "Research Tools", "Artificial Intelligence", "Productivity"]
image: "https://avatars.githubusercontent.com/u/27888654?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Zotero Model Context Protocol Connects Research Library to Claude, ChatGPT and More

Zotero has released the Model Context Protocol (MCP) integration, allowing its research library to be accessed directly from AI assistants such as Claude and ChatGPT.

## 🔍 Overview
- Connects Zotero library with Claude, ChatGPT, and other AI assistants via the Model Context Protocol.
- Enables searching, reading, citing, and annotating papers from within the AI chat.
- Supports semantic search using local, OpenAI, Gemini, or Ollama embeddings.

## 🧩 How it works
- A single package, `zotero-mcp-server`, provides three components: MCP server, CLI + agent skill, and Zotero Agent.
- MCP server communicates with chat apps that speak MCP but have no shell (Claude Desktop, ChatGPT, Cherry Studio, Chorus).
- CLI + agent skill is for agents with a shell (Claude Code, Codex, Cursor, Windsurf, Gemini CLI, Amp, OpenCode).
- Zotero Agent enables chatting inside Zotero next to the PDF you are reading.

| Component | Supported Apps |
|---|---|
| MCP server | Claude Desktop, ChatGPT, Cherry Studio, Chorus |
| CLI + agent skill | Claude Code, Codex, Cursor, Windsurf, Gemini CLI, Amp, OpenCode |
| Zotero Agent | Chat inside Zotero (next to PDF) |

## ⚙️ Key details
- Search by title, author, tag, collection, full text, or meaning (semantic search).
- Read metadata, BibTeX, full text, page ranges, and page images where text extraction garbles math, figures, and tables.
- Annotate highlights, area boxes, notes, and extract PDF annotations.
- Write: add papers by DOI, URL, ISBN, BibTeX, or file; manage collections and tags; merge duplicates.
- In local mode reads come straight from `zotero.sqlite`; writes go to the running Zotero 10+ or through the web API.
- Optional Scite citation tallies and retraction alerts.
- CLI + agent skill keeps 98 tokens in context until needed, instead of ~8k.
- Zotero Agent knows the item, page and selection you have open; answers link to pages.

## 🚀 Availability
- Requires Python 3.10+.
- Install with `uv tool install zotero-mcp-server` or `pip install zotero-mcp-server`.
- Setup commands: `zotero-mcp setup` (auto‑configures Claude Desktop), `zotero-mcp install-skill` for the CLI + agent skill, and install the `.xpi` in Zotero after adding the `zotero-cli` plugin for Zotero Agent.
- To enable Zotero's local API in Zotero 7+, open Settings → Advanced and tick *Allow other applications on this computer to communicate with Zotero*.
- One package ships all three components.

## 💡 Why it matters
- Provides direct access to a personal research library from AI chat interfaces.
- Enables semantic search and citation management without leaving the conversation.
- Handles PDF annotations, math, figures, and tables more accurately.
- Reduces context size for agents, keeping only 98 tokens until needed.

#Zotero #AIIntegration #ModelContextProtocol

---

*Source: [54yyyu/zotero-mcp](https://github.com/54yyyu/zotero-mcp)*
