---
title: "REA: AI‑Powered Reverse Engineering Across Binaries and Apps"
slug: "rea-aipowered-reverse-engineering-across-binaries-and-apps"
description: "Reverse engineer anything with agents, from app behavior down to native binaries. REA provides a single MCP for reverse engineering across binaries, applications, and runtime behavior."
date: 2026-10-13T22:07:53+05:30
tags: [ReverseEngineering, AIAgents, MCP, SoftwareAnalysis]
categories: ["AI", "Artificial Intelligence", "Software Development", "Security"]
image: "https://avatars.githubusercontent.com/u/76467478?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# REA: AI‑Powered Reverse Engineering Across Binaries and Apps

Reverse engineer anything with agents, from app behavior down to native binaries. REA provides a single MCP for reverse engineering across binaries, applications, and runtime behavior.

## 🔍 Overview
- "Reverse engineer anything with agents, from app behavior down to native binaries."
- "One MCP for reverse engineering across binaries, applications, and runtime behavior."
- "Your agent calls REA through MCP to inspect the target and trace relevant code."
- "REA returns findings with their evidence."

## 🧩 How it works
1. **Choose your agents** – supported agents include Claude Code, Codex, Cursor, Gemini CLI, Grok Build, and other agents.
2. **Setup registers REA with your agent and installs matching workflow instructions**.
3. **Setup adds REA's MCP server and matching workflow instructions, with backups of existing configuration**.
4. **Restart your agent afterward**.
5. The agent calls REA through the MCP, which inspects the target and traces relevant code, returning findings with evidence.

## ⚙️ Key details
- "Setup supports Claude Code, Codex, Cursor, Gemini CLI, Grok Build and other agents."
- "Native analysis can use an existing Hopper, Ghidra, or IDA installation; setup can optionally install Hopper with approval."
- "Static JavaScript analysis needs no native analysis engine."
- "For native analysis, configure a provider first."
- "See the CLI and Evidence guide for native commands, provider selection, snapshots and scripting."
- "REA changes quickly, and new releases include frequent bug fixes."
- "Keep your installation up to date."
- "Bun global updates require Bun 1.2.17 or later."
- "With an older Bun release, upgrade Bun manually before running rea update."
- "To refresh your agent registrations and skill, run the setup command printed by the update."
- "Review the setup changes and restart your agent."
- "For one‑off CLI commands, use `npx rea-agents@latest` followed by the command."
- "With Bun, use `bunx rea-agents@latest` in place of `npx rea-agents@latest`."

### Supported agents
| Supported Agent | Status |
|------------------|--------|
| Claude Code      | Supported |
| Codex            | Supported |
| Cursor           | Supported |
| Gemini CLI       | Supported |
| Grok Build       | Supported |
| other agents     | Supported |

## 🚀 Availability
- "Visit the REA website for setup instructions, illustrated guides, and real case studies."
- "See installation and setup for provider configuration and manual MCP registration."
- "For native analysis, configure a provider first."
- "Replace the path with your target, such as `D:/apps/example` on Windows."
- "Replace Notes with your target app and the feature you want to understand."
- "The result includes modules, imports, Electron boundaries and their evidence."

## 💡 Why it matters
- Enables developers and security researchers to understand how a feature works, down to the binary level, using familiar analysis tools and AI agents.
- Streamlines the workflow from agent selection to evidence generation, reducing manual setup and configuration effort.

#ReverseEngineering #AIAgents #MCP #SoftwareAnalysis

---

*Source: [morluto/rea](https://github.com/morluto/rea)*
