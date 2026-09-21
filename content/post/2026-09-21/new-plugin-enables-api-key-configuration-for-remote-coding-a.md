---
title: "New plugin enables API key configuration for remote coding agents controlled from phones"
slug: "new-plugin-enables-api-key-configuration-for-remote-coding-agents-controlled-from-phones"
description: "A new plugin has been introduced to solve a specific problem for developers running coding agents on remote machines controlled from their phones. It provides a way to configure API keys on those..."
date: 2026-09-21T18:02:01+05:30
tags: [CodexRemote, APIKeys, ChatGPT, CodingAgents, LLM]
categories: ["AI", "AI Agents", "Developer Tools", "Software Development"]
image: "https://static.simonwillison.net/static/2026-09-20/IMG_8168.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# New plugin enables API key configuration for remote coding agents controlled from phones

A new plugin has been introduced to solve a specific problem for developers running coding agents on remote machines controlled from their phones. It provides a way to configure API keys on those remote machines without pasting the keys directly into the ChatGPT app.

## 🧩 How it works

* **Remote control:** Codex Remote is used to run coding agents on various remote machines while controlling them from a mobile phone.
* **Securing keys:** To avoid pasting API keys directly into agent sessions, this plugin offers an alternative method to get keys onto the target machine.
* **Key input interface:** Running a specific command tells Codex to launch an interface and output a URL (which can include local network or Tailscale device IPs) to save additional API keys.
* **Command-line access:** The agent can later retrieve the configured keys programmatically when executing shell commands.

## ⚙️ Key details

The plugin utilizes specific commands to configure and retrieve API keys on remote machines:

| Command | Description |
| :--- | :--- |
| `uvx --with llm-keys-ui llm keys-ui --all` | Launches the interface and generates the URL used to save additional API keys. |
| `llm keys get anthropic` | Retrieves a saved key (such as an Anthropic key) for use within a shell command. |

![figure](https://static.simonwillison.net/static/2026-09-20/IMG_8166.jpeg)

![figure](https://static.simonwillison.net/static/2026-09-20/IMG_8167.jpeg)

#CodexRemote #APIKeys #ChatGPT #CodingAgents #LLM

---

*Source: [Release: llm-keys-ui 0.1](https://simonwillison.net/2026/Sep/20/llm-keys-ui/)*
