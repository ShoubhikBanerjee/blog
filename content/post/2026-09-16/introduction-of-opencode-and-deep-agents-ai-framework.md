---
title: "Introduction of OpenCode and Deep Agents AI Framework"
slug: "introduction-of-opencode-and-deep-agents-ai-framework"
description: "Deep Agents has released an open source agent harness and a corresponding coding agent called OpenCode. Built on the LangGraph orchestration framework, this development provides a structured approach..."
date: 2026-09-17T00:45:10+05:30
tags: [OpenCode, LangGraph, LangChain, DeepAgents, AIagents]
categories: ["AI", "AI Agents", "Software Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/66570915?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Introduction of OpenCode and Deep Agents AI Framework

Deep Agents has released an open source agent harness and a corresponding coding agent called OpenCode. Built on the LangGraph orchestration framework, this development provides a structured approach to creating agents capable of long-horizon, multi-step work.

## 🔍 Overview
OpenCode is an open source AI coding agent available as both a terminal tool and a desktop application. It is powered by Deep Agents, a higher-level package built on LangGraph that provides built-in capabilities for planning, filesystem usage, and sub-agent management.

## 🧩 How it works
Deep Agents acts as an opinionated harness on top of LangChain's `create_agent`. It utilizes LangGraph as the graph runtime to support streaming, persistence, and checkpointing. The system is compatible with any LLM that supports tool calling, including frontier APIs (OpenAI, Anthropic, Google), open-weight models (Baseten, Fireworks), and self-hosted models (Ollama, vLLM, llama.cpp).

## ⚙️ Key details
OpenCode includes specific agent roles and technical specifications:

| Agent/Feature | Description |
| :--- | :--- |
| build | Default, full-access agent for development work |
| plan | Read-only agent for analysis and code exploration; denies file edits by default |
| @general | General sub-agent for complex searches and multistep tasks |
| Sub-agents | Ability to delegate tasks to agents with isolated context windows |
| Filesystem | Read, write, edit, or search over local, sandboxed, or remote backends |
| Human-in-the-loop | Permission system to approve, edit, or reject tool calls |

## 🚀 Availability
OpenCode can be installed via various package managers and platforms:

**CLI Installation**
- npm: `npm i -g opencode-ai@latest`
- Homebrew: `brew install opencode` or `brew install anomalyco/tap/opencode`
- Scoop: `scoop install opencode`
- Chocolatey: `choco install opencode`
- Arch Linux: `sudo pacman -S opencode` or `paru -S opencode-bin`
- Nix: `nix run nixpkgs#opencode`
- Mise: `mise use -g opencode`
- Install script: `curl -LsSf https://langch.in/dcode | bash`

**Desktop Application**
- macOS: `opencode-desktop-mac-arm64.dmg` (Apple Silicon) and `opencode-desktop-mac-x64.dmg` (Intel)
- Windows: `opencode-desktop-windows-x64.exe`
- Linux: `.deb`, `.rpm`, or `.AppImage`
- Homebrew Cask: `brew install --cask opencode-desktop`
- Scoop: `scoop bucket add extras; scoop install extras/opencode-desktop`

**Installation Path Priority**
1. `$OPENCODE_INSTALL_DIR`
2. `$XDG_BIN_DIR`
3. `$HOME/bin`
4. `$HOME/.opencode/bin`

#OpenCode #LangGraph #LangChain #DeepAgents #AIagents

---

*Source: [anomalyco/opencode](https://github.com/anomalyco/opencode)*
*Source: [langchain-ai/langchain](https://github.com/langchain-ai/langchain)*
*Source: [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph)*
*Source: [langchain-ai/deepagents](https://github.com/langchain-ai/deepagents)*
