---
title: "Octocode: A Rust CLI and MCP server for codebase intelligence"
slug: "octocode-a-rust-cli-and-mcp-server-for-codebase-intelligence"
description: "Octocode is a Rust CLI and MCP server designed for exploring codebases by combining semantic search, structural search, and a live graph of symbols and dependencies. It provides AI agents, such as..."
date: 2026-11-24T22:08:41+05:30
tags: [Octocode, MCP, Rust, CodeIntelligence, AIAgents]
categories: ["AI", "AI Agents", "Developer Tools", "Search", "Programming"]
image: "https://avatars.githubusercontent.com/u/25336907?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Octocode: A Rust CLI and MCP server for codebase intelligence

Octocode is a Rust CLI and MCP server designed for exploring codebases by combining semantic search, structural search, and a live graph of symbols and dependencies. It provides AI agents, such as Claude Code, Codex, Cursor, and Windsurf, with deep understanding of code structures through a single binary.

## 🧩 How it works
The tool integrates several capabilities to assist with code exploration:
*   **Find code by intent:** Uses hybrid vector and keyword search with configurable reranking.
*   **Locate definitions and usages:** Performs structural search over the current source.
*   **Trace relationships:** Maps imports, calls, inheritance, and implementations between files and symbols.
*   **Read signatures:** Accesses function signatures without loading entire files, optionally using a language server for definitions, references, and hover information.
*   **Run locally:** Utilizes default embedding and reranking models or configurable remote providers.

## ⚙️ Key details
Octocode operates through specific tools that differ in their indexing requirements:

| Tool | Use it for | Requires an index |
|------|------------|-------------------|
| `semantic_search` | Find code, documentation, and indexed history by meaning | Yes |
| `structural_search` | Find definitions, usages, and AST patterns in current source | No |
| `view_signatures` | Read function signatures, declarations, and imports | No |
| `graphrag` | Explore live file and symbol relationships and dependency paths | No |
| `lsp_*` | Definitions, references, hover information, symbols, and completion | No; requires a language server |

Structural search, signatures, and the live dependency graph read the current source directly and function without an index. In contrast, semantic search relies on an index created by running commands in the project's Git repository. The default configuration uses local FastEmbed models, which download on first use without requiring an API key. For directories without Git, users can apply `octocode index --no-git`.

## 🚀 Availability
Installation methods include:
*   Using an installer on Linux or macOS, or in a Unix-compatible shell on Windows.
*   Downloading a binary from GitHub Releases or installing the published crate.
*   Building from source, which requires Rust 1.95 or later and `protoc`.

Users can integrate Octocode with various MCP clients by installing it where the client can find it on the `PATH` and adding an entry to the client's MCP configuration. Additionally, the companion AI agent runtime, Octomind, includes Octocode and OctoFS capabilities in its `developer:general` agent. The first run of Octomind may install required tools and ask for model credentials.

#Octocode #MCP #Rust #CodeIntelligence #AIAgents

---

*Source: [Muvon/octocode](https://github.com/Muvon/octocode)*
