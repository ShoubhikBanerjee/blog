---
title: "iCode Workbench Open-Source Agent Development Environment Update"
slug: "icode-workbench-open-source-agent-development-environment-update"
description: "iCode Workbench serves as the control room for a fleet of CLI agents, allowing users to run 44 launchable CLI agents in parallel. The environment features 21 agents with managed status hooks,..."
date: 2026-11-23T22:18:20+05:30
tags: [AIAgents, OpenSource, DeveloperTools, GitWorktrees]
categories: ["AI", "AI Agents", "Developer Tools", "Open Source"]
image: "https://avatars.githubusercontent.com/u/341013090?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# iCode Workbench Open-Source Agent Development Environment Update

iCode Workbench serves as the control room for a fleet of CLI agents, allowing users to run 44 launchable CLI agents in parallel. The environment features 21 agents with managed status hooks, alongside Claude Code, Codex, and OpenCode with native provider injection.

## 🔍 Overview
- Open-source agent development environment for Claude Code, Codex, OpenCode, and 40+ more CLI agents
- Pre-1.0 development stage
- Supports 44 CLI agents
- Multi-language support including English, 简体中文, 日本語, 한국어, Español, Português (BR), Deutsch, and Français

## 🧩 How it works
- Isolated Git worktrees by default where every change is reviewed in the checkout where it was made
- Run agents in parallel, each in its own Git worktree
- Task review remains a human decision
- Accepting a review records judgment without merging, pushing, or deleting anything
- Mira agent can propose, message, retry, and archive, but cannot approve a review, merge, or push
- Files, Search, and Source Control live beside the terminal, scoped to the checkout of the agent

## ⚙️ Key details
- System requirements include Node 24.x (.nvmrc pins 24.15.0), Corepack with pnpm 11.16.0, Git, and at least one harness on PATH
- Linux requirements include build-essential and python3; macOS requires Xcode Command Line Tools
- pnpm install rebuilds node-pty against Electron's ABI on Linux; Windows and macOS use Node-API prebuilds
- Database uses `icode.sqlite` running in WAL mode
- Unsigned installers trigger Windows SmartScreen and macOS Gatekeeper warnings on first launch

## 🚀 Availability
- Platforms supported: Pre-1.0 · Windows x64 · Linux x64 (WSL2/WSLg) · macOS x64 / arm64
- Linux packages: AppImage, deb, rpm
- Windows packages: NSIS installer
- macOS packages: x64 and arm64 dmg / zip
- License: AGPL-3.0

#AIAgents #OpenSource #DeveloperTools #GitWorktrees

---

*Source: [icodehq/icode-workbench](https://github.com/icodehq/icode-workbench)*
