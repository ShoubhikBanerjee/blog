---
title: "LCU Decouples Codex Computer Use for Any Agent Harness"
slug: "lcu-decouples-codex-computer-use-for-any-agent-harness"
description: "A new tool called LCU (Local Computer Use) has emerged, decoupling Codex's original computer-use runtime from the Codex app to make it usable inside any agent harness, without requiring Codex..."
date: 2026-11-17T22:09:21+05:30
tags: [LCU, ComputerUse, AIagents, Claude, DeveloperTools]
categories: ["AI", "AI Agents", "Developer Tools", "LLM", "Integrations"]
image: "https://avatars.githubusercontent.com/u/337367162?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LCU Decouples Codex Computer Use for Any Agent Harness

A new tool called LCU (Local Computer Use) has emerged, decoupling Codex's original computer-use runtime from the Codex app to make it usable inside any agent harness, without requiring Codex authentication.

## 🔍 Overview

LCU exposes the original Codex computer-use runtime to local harnesses. To function, the official ChatGPT desktop app must remain installed locally; it supplies the runtime and instructions, while LCU handles setup and integration.

## 🧩 How it works

- **Desktop Apps:** The system can read windows, click, type, and take screenshots.
- **Browsers:** When enabled, it can read and control Chrome tabs through the official extension, subject to site approval.
- **Approvals:** The first time an agent controls an app, the computer-use runtime asks the user to allow it.
- **Security:** Only the user can answer the approval pane; the model cannot see, press, or fake the pane.

## ⚙️ Key details

- **Harness Adapters:** Adapters are available for Pi, Codex CLI, and Claude Code, with experimental integrations for Oh My Pi, Hermes, DeepSeek Harness, and Junie.
- **Junie Limitations:** With Junie, the agent cannot show LCU's per-app prompt. Instead, it runs `lcu apps allow <App>` itself, and approval lasts permanently until the user revokes it.
- **High-Risk Apps:** Browsers and password managers display warnings from the runtime. Apps that Computer Use outright refuses, such as Terminal and iTerm2, are declined. The app hosting the agent is never approved.
- **CLI Management:** Users can review and change the approved app list from the terminal on macOS without opening the Codex app. Listing apps is free, but allowing or revoking requires the user to be at the machine.

| Integration | Details |
|---|---|
| **Claude Code** | Requires version 2.1.287 or newer. |
| **Claude App** | Register LCU through Claude Code (`lcu setup --agent claude-code`), not through Settings > Connectors. |
| **Claude Code Mod** | The `lcu-approve` mod asks approval questions natively as a card in the app and an approval pane in the terminal. |
| **Turn Limits** | In Claude Code, Computer Use normally ends when the turn that started it ends. A background subagent will be told "Computer Use is unavailable" unless an opt-in setting keeps it available for every turn of the session. |

## 🚀 Availability

- **Mac Requirements:** Requires an Apple Silicon Mac for Claude Code integration.
- **Setup:** Setup involves two commands through the Claude Code plugin manager.
- **Command:** Use `/computer-use-apps` to open an Approved apps panel in the terminal, displaying always-allowed apps with a Revoke option and an Allow field.

#LCU #ComputerUse #AIagents #Claude #DeveloperTools

---

*Source: [amontlabs/lcu](https://github.com/amontlabs/lcu)*
