---
title: "Anthropic Introduces Claude Code Agentic CLI and Model Updates"
description: "Claude Code is a new agentic CLI designed to read codebases, execute commands, and modify files using a layered system of permissions, hooks, MCP integrations, and subagents."
date: 2026-09-06T22:07:38+05:30
tags: [ClaudeCode, Anthropic, AIagents, CLI, DeveloperTools]
categories: [AI]
image: "https://blakecrosley.com/og/guide/claude-code.png?locale=es"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic Introduces Claude Code Agentic CLI and Model Updates

Claude Code is a new agentic CLI designed to read codebases, execute commands, and modify files using a layered system of permissions, hooks, MCP integrations, and subagents.

## 🧩 How it works

Claude Code utilizes various agents and permission modes to manage development tasks:

*   **Subagents:** These can run in the background by default. They are supported up to a default depth of 3 (configurable via `CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH=1` to disable) with a maximum of 20 concurrent subagents (`CLAUDE_CODE_MAX_CONCURRENT_SUBAGENTS`).
*   **Permission Modes:** The default permission mode is "Manual" across the CLI, VS Code, and JetBrains. However, "Auto" mode will be the default for new Pro, Max, and Team sessions starting August 14, 2026.
*   **Background Capabilities:** Background agents can commit, push, and open draft PRs upon completing code in a worktree. They utilize the Notification hook (`agent_needs_input`/`agent_completed`).

## ⚙️ Key details

Recent version updates have introduced the following technical changes:

| Version | Update/Feature |
| :--- | :--- |
| v2.1.198 | Subagents run in background by default; Claude in Chrome reaches general availability. |
| v2.1.199 | Supports up to 5 stacked slash-skill invocations; automatic retry for transient 429 errors for subscribers. |
| v2.1.202 | Adds "Dynamic workflow size" control in `/config` and separates `/review` from `/code-review`. |
| v2.1.203–205 | `/doctor` becomes a full diagnostic and correction review (alias `/checkup`). |
| v2.1.217 | Subagents stop generating their own subagents by default. |
| v2.1.218 | `/code-review` and skills with `context: fork` move to background subagents; `/deep-research` requires explicit invocation. |
| v2.1.219 | Re-enables nested subagents up to depth 3; adds `DirectoryAdded` hook and `sandbox.network.strictAllowlist`. |

## 🚀 Availability

Model availability and pricing vary by license and plan:

*   **Claude Opus 5:** Default for Max, Team Premium, Enterprise (from v2.1.251), and Anthropic API. It features a 1M context window, 128K maximum output, reasoning enabled by default, "high" default effort, and a knowledge cutoff of May 2026. Pricing is $5/$25 per MTok.
*   **Sonnet 5:** Default for Pro and Team Standard. It features a native 1M context window with a standard list price of $2/$10 per MTok.
*   **Fast Mode:** Available for Opus 5 and Opus 4.8 at $10/$50 per MTok.

#ClaudeCode #Anthropic #AIagents #CLI #DeveloperTools

---

*Source: [Guía de la CLI de Claude Code: instalación, configuración, comandos y variables de entorno](https://blakecrosley.com/es/guides/claude-code)*
