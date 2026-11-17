---
title: "Codex Router Connects Coding Clients to External Models"
slug: "codex-router-connects-coding-clients-to-external-models"
description: "Codex Router lets users connect external models to Codex and other coding clients through one local router. It stores provider credentials locally and can share one installation across clients, while..."
date: 2026-11-17T22:09:21+05:30
tags: [AI, CodingAgents, LLM, DeveloperTools]
categories: ["AI", "Artificial Intelligence", "Developer Tools", "AI Agents", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/108492647?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Codex Router Connects Coding Clients to External Models

Codex Router lets users connect external models to Codex and other coding clients through one local router. It stores provider credentials locally and can share one installation across clients, while native GPT access remains available with a valid ChatGPT login.

## 🔍 How it works

The Control Center manages provider connections, model visibility, usage, and service health. Setup asks which providers to enable and uses private local prompts for credentials. Some providers require selecting models from their live catalog before models appear.

| Client | Integration described |
|---|---|
| Codex App and CLI | Native and external models appear in the model picker; Linux support covers the CLI. |
| DeepSeek Harness | Managed provider routes are available in its settings. |
| Gemini CLI | Uses a managed endpoint, key, and default-model environment block. |
| Cursor Agent / Cursor App | A local Agent launcher is available; App BYOK uses a separately keyed public HTTPS edge. |
| Claude Code | Uses a separate `claude-router` launcher with the local Messages adapter. |
| OpenClaw | Uses a managed Responses provider. |
| opencode, pi, omp, Command Code, Hermes Agent | Provider configuration is published into the existing client. |

Built-in integrations include Anthropic, Kimi, DeepSeek, xAI, Z.ai, Qwen, MiniMax, Meta, OpenRouter, GitHub Copilot, and others. Available models depend on the provider, region, account entitlement, and local selection.

## ⚙️ Features and requirements

- Image, search, and subagent capabilities depend on the selected model route. Some features make additional provider requests and use additional quota.
- The default Codex setup uses Codex App or CLI. Using another integration requires installing its supported client.
- Node.js 22.19 or later is required; a maintained Node.js 24 LTS release is recommended.
- Git is used for managed checkout installation, updates, and rollback.
- The default compatibility-enabled source installation uses `uv` or Python 3.10 or later with `venv`. An explicit compatibility-layer opt-out skips Python installation and probes; source dependency setup follows the stored compatibility policy.
- Homebrew installs the formula's Python dependencies. On Windows, PowerShell must run in `FullLanguage` mode and policy must allow `Add-Type`.
- Building the macOS desktop companion locally requires the full Xcode app.

## 🚀 Setup and operation

Homebrew provides the router and CLI; the source installer is used for the desktop companion. Use `codex-router <command>` for Codex maintenance commands and `brew upgrade codex-router` for updates.

After provider setup, run the doctor from the installed checkout and resolve any `FAIL`. On macOS or Linux, the command is `./bin/model-router codex doctor`. Live inference tests run only when explicitly requested and consume quota from the selected provider.

Fully quit and reopen Codex, create a new task, and choose the intended model. Codex reads the router's model catalog at startup. If a model is missing, check provider selection, authentication, and model visibility before reinstalling. Native GPT models also require a usable ChatGPT login.

Open **Codex Router** to access the Control Center. Closing its window normally leaves the tray running; use the tray or menu-bar entry to reopen it. macOS uses a native menu-bar host with an embedded Electron window, while Windows and Linux use an Electron window and tray.

#AI #CodingAgents #LLM #DeveloperTools

---

*Source: [duolahypercho/codex-router](https://github.com/duolahypercho/codex-router)*
