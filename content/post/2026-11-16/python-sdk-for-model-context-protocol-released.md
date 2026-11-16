---
title: "Python SDK for Model Context Protocol Released"
slug: "python-sdk-for-model-context-protocol-released"
description: "The official Python SDK for Model Context Protocol servers and clients has been released, providing a Python implementation of the Model Context Protocol (MCP). The documentation is available at..."
date: 2026-11-16T22:14:27+05:30
tags: [PythonSDK, ModelContextProtocol, LLMApplications, AITools]
categories: ["AI", "Artificial Intelligence", "Software Development", "APIs", "Python"]
image: "https://avatars.githubusercontent.com/u/182288589?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Python SDK for Model Context Protocol Released

The official Python SDK for Model Context Protocol servers and clients has been released, providing a Python implementation of the Model Context Protocol (MCP). The documentation is available at <https://py.sdk.modelcontextprotocol.io/>, including a Get started guide, What's new in v2, the API reference, and a migration guide.

## 🔍 Overview
- The Model Context Protocol lets you build servers that expose data and functionality to LLM applications in a secure, standardized way.
- Think of it like a web API, but designed for LLM interactions.

## 🧩 How it works
- Build MCP servers that expose tools, resources, and prompts to any MCP host.
- Build MCP clients that connect to any MCP server.
- Speak every standard transport: stdio, Streamable HTTP, and SSE.
- Python 3.11+ is required.

## ⚙️ Key details
- The `cli` extra adds the `mcp` command-line tool (`mcp dev`, `mcp run`, `mcp install`) on top of the SDK; install plain `mcp` if you don't need it.
- For one-off commands, `uv run --with "mcp[cli]" mcp ...` works without a project.
- Example usage: Add two numbers or greet someone by name.
- That's a complete MCP server: one tool, one templated resource.
- Call `add` with `a=1`, `b=2` and you get `3` back.
- Notice what you did **not** write: no JSON Schema (`a: int, b: int` _is_ the schema), no request parsing, no validation code, no protocol handling.
- Two type-hinted Python functions and a docstring.
- The same package is a full MCP **client**.
- A URL means Streamable HTTP, the transport you deploy.
- `Client` can also launch a local server as a stdio subprocess or take any custom transport.

## 🚀 Availability
- The project is licensed under the MIT License.
- Contributions are welcome; see the [contributing guide](https://github.com/modelcontextprotocol/python-sdk/blob/main/CONTRIBUTING.md) to get started.

## 💡 Why it matters
- The SDK simplifies building and connecting to MCP servers and clients, reducing the need for manual request parsing, validation, and protocol handling.
- It supports various transports, making it versatile for different deployment scenarios.
- The project aims to support contributors of all levels of experience.

#PythonSDK #ModelContextProtocol #LLMApplications #AITools

---

*Source: [modelcontextprotocol/python-sdk](https://github.com/modelcontextprotocol/python-sdk)*
