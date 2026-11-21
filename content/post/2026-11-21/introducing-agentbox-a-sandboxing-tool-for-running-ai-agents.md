---
title: "Introducing Agentbox, a Sandboxing Tool for Running AI Agents in Docker"
slug: "introducing-agentbox-a-sandboxing-tool-for-running-ai-agents-in-docker"
description: "A new project called `agentbox` has been introduced to help developers run AI agents inside secure sandboxes. This project is currently in early-stage development, meaning users may experience..."
date: 2026-11-21T22:09:40+05:30
tags: [AIAgents, Sandboxing, Docker, DeveloperTools, Security]
categories: ["AI", "AI Agents", "Software Development", "Cybersecurity"]
image: "https://avatars.githubusercontent.com/u/168657?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Introducing Agentbox, a Sandboxing Tool for Running AI Agents in Docker

A new project called `agentbox` has been introduced to help developers run AI agents inside secure sandboxes. This project is currently in early-stage development, meaning users may experience breaking changes between releases.

## 🔍 Overview

The tool is designed to work with any Docker-compatible runtime. To run it, you need a VM and Docker installed. While setting this up can be done in a variety of ways, the provided instructions are for Colima. To install it, download the `agentbox` binary from [GitHub Releases](https://github.com/mattolson/agent-sandbox/releases); the installer defaults to the `~/.local/bin` directory.

## 🧩 How it works

When initializing, the tool simplifies the process of configuring and running agents:
- **Interactive Setup**: It prompts interactively for the project name, agent, mode, and IDE when needed. It then generates the docker compose and network policy files for the sandbox.
- **Secrets Directory**: It automatically creates the host secret directory at `~/.config/agent-sandbox/secrets` (with mode `0700`) if it is missing. On version 0.17.0 and earlier, you must create this directory yourself before starting the sandbox.
- **Read-Only Proxy**: The proxy mounts the secrets directory as read-only, even if you do not have any secrets yet.
- **Configuration Auditing**: To inspect your configuration after initialization, you can run `agentbox policy config` to output the effective network policy, or `agentbox compose config` for the combined docker compose stack.
- **Yolo Mode**: Because you are running the agent inside a dedicated sandbox, you can even try yolo mode!

## ⚙️ Key details

Depending on the agent image you are using, you should follow its specific setup instructions. Additionally, developers should be aware of several extension and IDE limitations within the sandbox environment:

| Tool or Plugin | Compatibility Status |
| :--- | :--- |
| Copilot's IntelliJ plugin | [Cannot complete auth in a devcontainer](https://github.com/microsoft/copilot-intellij-feedback/issues/1375) |
| Google Gemini | No official plugin available for JetBrains |
| OpenCode | No JetBrains extension available |
| Pi | No IDE extensions available |
| Hermes | No IDE extensions available |

#AIAgents #Sandboxing #Docker #DeveloperTools #Security

---

*Source: [mattolson/agent-sandbox](https://github.com/mattolson/agent-sandbox)*
