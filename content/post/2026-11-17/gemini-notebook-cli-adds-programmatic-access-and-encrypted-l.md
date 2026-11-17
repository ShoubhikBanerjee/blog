---
title: "Gemini Notebook CLI adds programmatic access and encrypted login storage"
slug: "gemini-notebook-cli-adds-programmatic-access-and-encrypted-login-storage"
description: "Gemini Notebook now offers programmatic access via a command-line interface (CLI), Model Context Protocol (MCP) server, and AI agent skills. This update also introduces an option to encrypt Google..."
date: 2026-11-17T22:09:21+05:30
tags: [GeminiNotebook, CLI, MCP, AIAgents, Security]
categories: ["AI", "AI Agents", "Developer Tools", "Security", "Cloud Computing"]
image: "https://avatars.githubusercontent.com/u/47641890?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Gemini Notebook CLI adds programmatic access and encrypted login storage

Gemini Notebook now offers programmatic access via a command-line interface (CLI), Model Context Protocol (MCP) server, and AI agent skills. This update also introduces an option to encrypt Google login credentials in a computer's keychain.

## 🧩 How it works
Programmatic access to Gemini Notebook is available through three methods:
- Command-line interface (CLI)
- Model Context Protocol (MCP) server
- AI agent skills

Users can connect tools in three commands:
1. Install (provides `nlm` and the MCP server): `uv tool install notebooklm-mcp-cli`
2. Sign in to Google account: `nlm login`
3. Connect AI tools: `nlm setup`

## 🔐 Security details
Saved Google logins can now be encrypted with the key kept in the computer's keychain instead of a plain file. This feature is optional and changes nothing unless explicitly enabled.

- Recommended for personal computers: `nlm auth storage set protected`
- Alternative: Use the `nlm setup` wizard and select the 'Credentials Protection' option.
- Servers, cron, Docker, and SSH setups can keep the plain file.
- Personal and consumer accounts are tested regularly.

## ⚙️ Enterprise support
Gemini Notebook Enterprise support is currently experimental. The documented `notebook.cloud.google.com` host has been live-verified with a project-qualified `global` deployment. Other Enterprise host variants may require additional validation.

## 🎬 Demo resources
The developer notes the tool is free and built in spare time, with a coffee helping cover the real time and resources required for testing every Gemini Notebook feature. A collection of videos demonstrates various aspects of the workflow:

| Duration | Description |
| :--- | :--- |
| 5 min | Start with Claude |
| 22 min | The full build, start to finish |
| 16 min | Wizard, doctor, and mcpb |
| 8 min | A local model, same notebook |
| 15 min | One server, many front ends |
| 14 min | Codex and NotebookLM, end to end |
| 2 min | A two-minute taste of the workflow |
| 11 min | Every style, side by side |
| 13 min | Create, query, and download from the CLI |
| 10 min | See what happens with MCP access |
| 12 min | The story behind the CLI and server |
| 16 min | The original end-to-end overview |

#GeminiNotebook #CLI #MCP #AIAgents #Security

---

*Source: [jacob-bd/gemini-notebook-mcp-cli](https://github.com/jacob-bd/gemini-notebook-mcp-cli)*
