---
title: "Microsoft publishes open-source Model Context Protocol curriculum and Qdrant memory server"
slug: "microsoft-publishes-open-source-model-context-protocol-curriculum-and-qdrant-memory-server"
description: "Microsoft has released an open-source curriculum for the Model Context Protocol (MCP) alongside an official MCP server for Qdrant, enabling developers to build modular, secure AI workflows and..."
date: 2026-11-20T22:08:48+05:30
tags: [MCP, Microsoft, Qdrant, AIDevelopment, OpenSource]
categories: ["AI", "AI Development", "Open Source", "MCP", "Vector Databases"]
image: "https://avatars.githubusercontent.com/u/6154722?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft publishes open-source Model Context Protocol curriculum and Qdrant memory server

Microsoft has released an open-source curriculum for the Model Context Protocol (MCP) alongside an official MCP server for Qdrant, enabling developers to build modular, secure AI workflows and implement semantic memory layers using specific language examples and vector search integration.

## 🧩 The MCP Curriculum
The new open-source curriculum introduces the fundamentals of MCP through real-world, cross-language examples. It is designed for developers to learn practical techniques for building modular, scalable, and secure AI workflows, covering everything from session setup to service orchestration.

- **Languages Covered**: C#, Java, JavaScript, Rust, Python, and TypeScript.
- **Repository**: The resources are hosted at `https://github.com/microsoft/mcp-for-beginners.git`.
- **Global Accessibility**: The repository includes more than 50 language translations. Note that these translations significantly increase the download size.
- **Community Support**: Developers can join the Microsoft Foundry Discord community using the provided link.

## 🧠 The Qdrant MCP Server
The release includes an official Model Context Protocol server for keeping and retrieving memories in the Qdrant vector search engine. This server acts as a semantic memory layer on top of the Qdrant database and is based on FastMCP.

### Core Tools
- `qdrant-store`: Stores information in the Qdrant database.
- `qdrant-find`: Retrieves relevant information from the Qdrant database.

### Configuration Details
Configuration is handled via environment variables, and the only command-line argument is `--transport`, which selects the transport protocol. You cannot provide both `QDRANT_URL` and `QDRANT_LOCAL_PATH` simultaneously.

| Environment Variable | Description |
| :--- | :--- |
| `QDRANT_LOCAL_PATH` | Path to the local Qdrant database (alternative to `QDRANT_URL`) |
| `EMBEDDING_PROVIDER` | Embedding provider to use (currently only "fastembed" is supported) |
| `EMBEDDING_MODEL` | Name of the embedding model to use |
| `QDRANT_SEARCH_LIMIT` | Maximum number of results to return from search |
| `QDRANT_READ_ONLY` | Enable read-only mode (disables `qdrant-store` tool) |
| `FASTMCP_HOST` | Host address to bind the server to (SSE and HTTP transports) |
| `FASTMCP_PORT` | Port to run the server on (SSE and HTTP transports) |
| `FASTMCP_MASK_ERROR_DETAILS` | Hide exception details from tool error messages sent to clients |

### Naming Conventions
Before version 0.9.0, settings used the `FASTMCP_SERVER_` prefix (e.g., `FASTMCP_SERVER_HOST`). The old names `FASTMCP_SERVER_HOST`, `FASTMCP_SERVER_PORT`, and `FASTMCP_SERVER_DEBUG` still work but are deprecated and will be removed in a future release. If both old and new names are set, the new name takes precedence.

## 🚀 Availability and Usage
The `mcp-server-qdrant` can be run directly without specific installation steps by using `uvx`. The server supports different transport protocols specified using the `--transport` flag.

#MCP #Microsoft #Qdrant #AIDevelopment #OpenSource

---

*Source: [microsoft/mcp-for-beginners](https://github.com/microsoft/mcp-for-beginners)*
*Source: [qdrant/mcp-server-qdrant](https://github.com/qdrant/mcp-server-qdrant)*
