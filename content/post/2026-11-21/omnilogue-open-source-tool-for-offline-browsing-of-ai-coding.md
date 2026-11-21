---
title: "Omnilogue Open-Source Tool for Offline Browsing of AI Coding Assistant History"
slug: "omnilogue-open-source-tool-for-offline-browsing-of-ai-coding-assistant-history"
description: "Omnilogue is an open‑source desktop application with an optional self‑hosted WebUI that lets you browse, search, and analyze the history of many AI coding assistants while keeping all data local."
date: 2026-11-21T18:08:57+05:30
tags: [Omnilogue, AIHistory, OpenSource]
categories: ["AI", "Software Development", "Artificial Intelligence", "Open Source"]
image: "https://avatars.githubusercontent.com/u/60695299?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Omnilogue Open-Source Tool for Offline Browsing of AI Coding Assistant History

Omnilogue is an open‑source desktop application with an optional self‑hosted WebUI that lets you browse, search, and analyze the history of many AI coding assistants while keeping all data local.

## 🔍 Overview
- Desktop app and web server to browse, search and analyze AI coding assistant history — Claude Code, Codex CLI, GitHub Copilot, Gemini CLI, Cursor, OpenCode and more.
- 100 % offline; the app reads conversation files on disk and does not upload session data or require an Omnilogue account.
- Supports a long list of assistants, including Aider, Amazon Q CLI, Antigravity, Claude Code, Cline, CodeBuddy, Codex CLI, Continue.dev, Cursor, ForgeCode, Gemini CLI, GitHub Copilot, OpenCode, OpenHands, PearAI, Pi, Qoder, Qwen Code, Zed, and many others.

## 🧩 How it works
- The desktop app reads local conversation files; an optional server can be run on the same machine for browser access.
- Example server binds to loopback only and is reachable at `http://127.0.0.1:3727`.
- Server guide covers prebuilt binaries, Docker, and authentication for network access.
- Technical requirements: Node.js 20.19+ (or 22.12+), pnpm, and a stable Rust toolchain. Linux build prerequisites are listed in the Linux guide.
- Build the desktop bundle with `pnpm tauri:build`.

## ⚙️ Key details
- **Platforms**: macOS (Apple silicon and Intel), Windows x64, Linux x86‑64.
- **Installation**: desktop download for each platform; macOS Homebrew support; Flatpak and other Linux packages via the Linux guide.
- **Updates**: existing installs can update in place while keeping favorites and settings.
- **Usage insights**: review tokens and estimated API costs where logs provide data; separate visibility into sub‑agent work.
- **Session navigation**: find conversations again, browse by project or assistant, search across sessions, follow conversation branches, jump between steps, and inspect tool calls and file edits.

## 🚀 Availability
- Download links are provided for each supported OS.
- macOS users may also install via Homebrew.
- Linux users can use Flatpak or follow the Linux guide for other package managers.
- The optional WebUI server can be run locally; see the server guide for details.

## 💡 Why it matters
- Keeps AI coding assistant history fully local, protecting privacy and avoiding external accounts.
- Independent project, not affiliated with any of the assistants whose history it reads, offering a neutral tool for developers to review their own AI‑assisted work.

#Omnilogue #AIHistory #OpenSource

---

*Source: [jhlee0409/omnilogue](https://github.com/jhlee0409/omnilogue)*
