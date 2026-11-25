---
title: "MCPM v2.0 releases a global configuration model for MCP servers"
slug: "mcpm-v2-0-releases-a-global-configuration-model-for-mcp-servers"
description: "MCPM v2.0 has been released as an open source CLI tool for managing Model Context Protocol (MCP) servers. This version eliminates the complexity of the v1 target-based system in favor of a clean..."
date: 2026-11-25T22:10:10+05:30
tags: [MCPM, MCP, CLI, OpenSource, DeveloperTools]
categories: ["AI", "AI Agents", "Developer Tools", "Open Source", "Model Context Protocol"]
image: "https://avatars.githubusercontent.com/u/205121201?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# MCPM v2.0 releases a global configuration model for MCP servers

MCPM v2.0 has been released as an open source CLI tool for managing Model Context Protocol (MCP) servers. This version eliminates the complexity of the v1 target-based system in favor of a clean global workspace model, allowing users to install servers once and organize them with profiles before integrating them into various MCP clients.

## 🔍 Overview
MCPM provides a simplified approach to managing MCP servers through a global configuration model. Instead of managing individual targets, users can now install servers once and use them everywhere. The tool is designed to be AI Agent Friendly, offering a non-interactive CLI with comprehensive automation support and an llm.txt guide.

## 🧩 How it works
The v2.0 architecture uses a global configuration model where servers are installed once and organized with virtual profiles. These profiles act as tags to organize servers into logical groups for different workflows. Once organized, servers can be integrated into specific MCP clients as needed.

## ⚙️ Key details
Key features of MCPM v2.0 include:

- **Global Server Management**: Install servers once, use everywhere
- **Virtual Profiles**: Organize servers with tags for different workflows
- **Server Discovery**: Browse and install from the MCP Registry
- **Direct Execution**: Run servers over stdio or HTTP for testing
- **Public Sharing**: Share servers through secure tunnels
- **Server Updates**: Check for and apply updates to git-based, NPX, and binary servers
- **Client Integration**: Manage configurations for Claude Desktop, Cursor, Windsurf, and more
- **AI Agent Friendly**: Non-interactive CLI with comprehensive automation support and llm.txt guide
- **Beautiful CLI**: Rich formatting and interactive interfaces
- **Usage Analytics**: Monitor server usage and performance

## 🚀 Supported Clients
MCPM supports managing MCP servers for the following clients:

| Client | Provider |
| :--- | :--- |
| Claude Desktop | Anthropic |
| Cursor | - |
| Windsurf | - |
| Vscode | - |
| Cline | - |
| Continue | - |
| Goose | - |
| 5ire | - |
| Roo Code | - |
| OpenCode | - |

#MCPM #MCP #CLI #OpenSource #DeveloperTools

---

*Source: [pathintegral-institute/mcpm.sh](https://github.com/pathintegral-institute/mcpm.sh)*
