---
title: "FastMCP 3.2 Adds AI‑Assisted Search to Calibre Library"
slug: "fastmcp-3-2-adds-aiassisted-search-to-calibre-library"
description: "FastMCP 3.2 extends Calibre e‑book library with AI‑assisted search, RAG, and agentic workflows."
date: 2026-11-28T22:07:57+05:30
tags: [Calibre, AI, LanceDB, SemanticSearch, Python]
categories: ["AI", "Software", "Artificial Intelligence", "Data Management", "Python"]
image: "https://avatars.githubusercontent.com/u/34750307?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# FastMCP 3.2 Adds AI‑Assisted Search to Calibre Library

FastMCP 3.2 extends Calibre e‑book library with AI‑assisted search, RAG, and agentic workflows.

## 🔍 Overview
- AI‑assisted search, Retrieval‑Augmented Generation (RAG), and agentic workflows for Sandra's 1000+ book library.
- Exposes 33 portmanteau tools for natural‑language library management.
- Built into Calibre’s core engine.

## 🧩 How it works
- Bridges Calibre e‑book library and AI assistants (Claude Desktop, Cursor, etc.) via the Model Context Protocol.
- Reads Calibre’s metadata.db directly and indexes metadata for semantic search using LanceDB.
- Provides Incremental LanceDB RAG Sync and Reciprocal Rank Fusion (RRF) hybrid search.
- Offers a 21‑tool registry and a portmanteau CRUD & Library Health Engine.

## ⚙️ Key details
- FastMCP 3.2 Server (port :10720) and WebApp (Next.js 15 on :10721).
- Calibre GUI + Plugin (Qt6 / PyQt5). 
- FastAPI REST layer with async background workers.
- CALIBRE CONTENT SERVER (e.g., :8099, http://goliath:8099/ or http://localhost:8080/).
- Async Python Engine (calibre.srv) and RapydScript SPA (index-generated.html).
- HTML5 In‑Browser Reader (viewer.js / offline SW) and OPDS Mobile Catalog Feed.
- Databases: metadata.db (Calibre SQLite catalog), full-text-search.db (FTS5 token index), calibre_mcp_data.db (sidecar extended metadata).
- Semantic search powered by LanceDB, fastembed (BAAI/bge-small), and Ollama/OpenAI providers.

## 🚀 Availability
- Download Calibre MCP_*_x64-setup.exe from Releases, double‑click to launch Calibre MCP.
- Claude Desktop one‑liner: download calibre‑mcp.mcpb from Releases and install via Settings → MCP Servers → Install from file.
- After installation, use prompts such as "Find unread sci‑fi books", "Open a random Banks novel", or "What's my library health?".

## 💡 Why it matters
- Provides AI‑powered semantic search and natural‑language library management directly within Calibre.
- Enables RAG and agentic workflows to help users navigate large e‑book collections efficiently.

#Calibre #AI #LanceDB #SemanticSearch #Python

---

*Source: [sandraschi/calibremcp](https://github.com/sandraschi/calibremcp)*
