---
title: "MCP Reference Repository Updates SDK Support and Archives Legacy Servers"
slug: "mcp-reference-repository-updates-sdk-support-and-archives-legacy-servers"
description: "The Model Context Protocol (MCP) reference implementations repository has been reorganized to strictly house reference servers maintained by the MCP steering group, while archiving legacy projects..."
date: 2026-11-18T12:19:35+05:30
tags: [ModelContextProtocol, MCPSDK, LLMTools, ReferenceImplementation]
categories: ["AI", "LLM Infrastructure", "Developer Tools", "API Protocols", "Open Source"]
image: "https://avatars.githubusercontent.com/u/182288589?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# MCP Reference Repository Updates SDK Support and Archives Legacy Servers

The Model Context Protocol (MCP) reference implementations repository has been reorganized to strictly house reference servers maintained by the MCP steering group, while archiving legacy projects and expanding SDK support across multiple programming languages.

## 🧩 How it works
The servers in this repository are intended as reference implementations to demonstrate MCP features and SDK usage. They serve as educational examples for developers building their own MCP servers, rather than production-ready solutions. These implementations showcase how MCP can give Large Language Models (LLMs) secure, controlled access to tools and data sources.

Each MCP server is typically implemented using an MCP SDK. The repository currently references the following SDKs:
- C# MCP SDK
- Go MCP SDK
- Java MCP SDK
- Kotlin MCP SDK
- PHP MCP SDK
- Python MCP SDK
- Ruby MCP SDK
- Rust MCP SDK
- Swift MCP SDK
- TypeScript MCP SDK

## ⚙️ Key details
The active reference servers in the main repository include:
- **Everything**: Reference/test server with prompts, resources, and tools.
- **Fetch**: Web content fetching and conversion for efficient LLM usage.
- **Filesystem**: Secure file operations with configurable access controls.
- **Git**: Tools to read, search, and manipulate Git repositories.
- **Memory**: Knowledge graph-based persistent memory system.
- **Sequential Thinking**: Dynamic and reflective problem-solving through thought sequences.
- **Time**: Time and timezone conversion capabilities.

## 📦 Archival and Registry
The following reference servers have been archived and moved to the `servers-archived` repository:
- **AWS KB Retrieval**: Retrieval from AWS Knowledge Base using Bedrock Agent Runtime.
- **Brave Search**: Web and local search using Brave's Search API.
- **PostgreSQL**: Read-only database access with schema inspection.

For developers looking for a broader list of MCP servers, published servers can be browsed on the MCP Registry. TypeScript-based servers in the active repository can be started using `npx`.

#ModelContextProtocol #MCPSDK #LLMTools #ReferenceImplementation

---

*Source: [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers)*
