---
title: "150+ CLI Coding Agents Curated"
slug: "150-cli-coding-agents-curated"
description: "A curated list of 150+ CLI coding agents has been published, detailing AI-powered tools that operate within the terminal, as well as the harnesses used to orchestrate, sandbox, or extend them. These..."
date: 2026-11-17T06:20:51+05:30
tags: [CLI, AIagents, coding, terminal, openSource]
categories: ["AI", "AI Agents", "Developer Tools", "Open Source", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/46579244?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# 150+ CLI Coding Agents Curated

A curated list of 150+ CLI coding agents has been published, detailing AI-powered tools that operate within the terminal, as well as the harnesses used to orchestrate, sandbox, or extend them. These agents differ from chat-based assistants by having direct access to the filesystem, shell, and development tools, enabling them to autonomously read, write, and execute code, edit files, run tests, commit changes, and iterate on errors.

## 🔍 Overview
CLI coding agents are AI-powered tools designed to run in the terminal. They are capable of autonomously reading, writing, and executing code within a repository. Their primary distinction from standard chat assistants is their direct access to local development environments, including the filesystem and shell, which allows for direct interaction with development tools.

## 🧩 Notable Agents
The following table lists specific CLI coding agents and harnesses highlighted in the evidence, including their GitHub star counts and key features.

| Agent | Stars | Key Features |
| :--- | :--- | :--- |
| Hermes Agent | 264k | Self-improving CLI agent with persistent memory, automated skill creation, sandboxed code execution via Unix socket RPC, and multi-platform reach (Telegram/Slack/Discord/WhatsApp). Supports 300+ models across multiple providers. |
| OpenCode | 227k | Terminal-native coding agent with 75+ provider support, LSP integration, and privacy-first design. Formerly opencode-ai; now at opencode.ai. |
| Claw Code | 195k | Clean-room Python/Rust rewrite of Claude Code architecture using oh-my-codex. Described as the fastest repo in GitHub history to 100K stars. Born from the March 2026 Claude Code source leak. |
| Codex CLI | 136k | OpenAI's local coding agent for reading/editing/running code, featuring an interactive TUI and tool execution. |
| Pi | 122k | Minimal, adaptable terminal coding harness from the pi-mono toolkit with a unified LLM API, TUI, skills, and MCP support. |
| Gemini CLI | 109k | Google's terminal agent powered by Gemini, with tools for repo work and research. |
| OpenHands | 93.6k | Open-source agentic developer environment (formerly OpenDevin) with CLI and web entrypoints, plus a lightweight CLI-only package. |
| Cline CLI | 71.7k | Model-agnostic autonomous agent for planning, file edits, command execution, and browser use. |
| Oh My OpenAgent | 70.9k | Multi-harness agent OS layered over OpenCode, Codex, and Pi. Team Mode runs several models on one job, with a hash-anchored tool harness and heavy context tuning. |
| Open Interpreter | 68.9k | Terminal tool that can execute code and actions, often used as a "do things on my machine" agent. |
| Goose | 56.7k | Local, extensible agent that can execute, edit, and test; designed to run on-device and integrate with MCP. |
| Aider | 50.1k | Pair-programming agent for editing files via diffs/patches, with strong git and multi-file workflows. |
| Codewhale | 41.2k | Rust terminal coding agent (formerly deepseek-tui) supporting bring-your-own-model across 30+ providers plus local vLLM/SGLang/Ollama. |
| OH-MY-PI | 39.2k | Terminal coding agent ("Pi") with a TypeScript/Rust monorepo and local-first ergonomics. |
| Continue CLI | 36.5k | Open-source terminal extension for multi-model coding with a local/privacy focus. |
| Reasonix | 36.1k | Single Go binary coding agent built for long unattended runs, featuring one local engine with four entry points (terminal, desktop app, browser, or editor over ACP). |

## ⚙️ Key Details
Specific implementations within the list include unique architectural and operational features:

*   **Codewhale:** Offers a TUI or headless `codewhale exec` for scripts and CI. Fleets can pin a different provider, model, and reasoning tier per role, allowing a cheap model to direct an expensive one. It includes workspace snapshots, `/undo` functionality, and a three-level permission posture.
*   **Reasonix:** Utilizes config-driven providers defined in `reasonix.toml`.
*   **Claw Code:** Developed as a clean-room rewrite of the Claude Code architecture using oh-my-codex.
*   **Hermes Agent:** Employs sandboxed code execution via Unix socket RPC and supports persistent memory and automated skill creation.

#CLI #AIagents #coding #terminal #openSource

---

*Source: [bradAGI/awesome-cli-coding-agents](https://github.com/bradAGI/awesome-cli-coding-agents)*
