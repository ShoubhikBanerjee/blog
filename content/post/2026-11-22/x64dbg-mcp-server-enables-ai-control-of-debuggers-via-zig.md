---
title: "x64dbg-MCP Server enables AI control of debuggers via Zig"
slug: "x64dbg-mcp-server-enables-ai-control-of-debuggers-via-zig"
description: "The x64dbg-MCP Server, a native MCP (Model Context Protocol) plugin for x64dbg, has been released, allowing MCP-compatible AI assistants to control the debugger programmatically over HTTP. Built with..."
date: 2026-11-22T22:08:30+05:30
tags: [x64dbg, MCP, Zig, AIAssistants, Debugging]
categories: ["AI", "Developer Tools", "AI Agents", "Cybersecurity", "Programming Languages"]
image: "https://avatars.githubusercontent.com/u/3162883?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# x64dbg-MCP Server enables AI control of debuggers via Zig

The x64dbg-MCP Server, a native MCP (Model Context Protocol) plugin for x64dbg, has been released, allowing MCP-compatible AI assistants to control the debugger programmatically over HTTP. Built with the Zig programming language, the solution is designed to be dependency-free, requiring only a single binary drop-in deployment without the need for .NET, Python, or other runtimes.

## 🧩 How it works
The server exposes the full functionality of x64dbg through standard protocols, enabling AI agents to perform complex debugging tasks. It supports both Streamable HTTP and SSE (Server-Sent Events) transports using JSON-RPC 2.0, ensuring compatibility with both new and legacy MCP clients.

- **Transport Protocols**: Uses Streamable HTTP + SSE for dual-transport compatibility.
- **Authentication**: Implements mandatory Bearer token authentication; the token is auto-generated on the first run and required for every request to prevent unauthorized access.
- **Execution**: The plugin is a pure native application with zero dependencies, cross-compiling to both x32 and x64 architectures from a single codebase.

## ⚙️ Key details
The MCP server provides extensive control over the debugging environment, covering a wide range of operations from code analysis to memory management.

- **MCP Tools**: The evidence cites 84 MCP tools for full debugger control, including disassembly, stepping, breakpoints, memory allocation, registers, modules, threads, call stack, pattern scanning, string extraction, xrefs, symbols, bookmarks, PE analysis, OEP detection, module dumping, PEB/SEH inspection, and tracing. *(Note: One quote also references 72 MCP tools covering the workflow).*
- **Event Callbacks**: Includes 22 event callbacks covering init, stop, breakpoint, exception, step, attach/detach, DLL load/unload, and thread events.
- **Configuration**: Users can change IP, port, and token settings via a dialog in the Plugins menu, which auto-restarts the server upon saving.
- **Auto-Start**: The MCP server initiates automatically when x64dbg launches.

| Component | Details |
| :--- | :--- |
| **Default Port (x64)** | 0.0.0.0:9094 |
| **Default Port (x32)** | 0.0.0.0:9095 |
| **Language** | Zig |
| **Dependencies** | None (No .NET, Python, or runtimes) |
| **Architectures** | x32 and x64 |

## 🚀 Availability
Deployment is designed to be straightforward, allowing users to build and deploy the plugin across different operating systems.

1. Copy the contents of the `dist/` directory into the x64dbg root folder to deploy both x32 and x64 versions.
2. Launch x64dbg; the MCP server starts automatically.
3. For connections from WSL or remote machines, set the bind address to `0.0.0.0` in the config dialog and use the host's IP address.

The tool supports cross-compiling Windows plugins from Linux, macOS, or WSL environments from a single command.

#x64dbg #MCP #Zig #AIAssistants #Debugging

---

*Source: [duty1g/x64dbg-mcp-server](https://github.com/duty1g/x64dbg-mcp-server)*
