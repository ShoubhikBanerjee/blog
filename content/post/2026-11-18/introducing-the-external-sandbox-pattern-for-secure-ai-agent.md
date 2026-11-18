---
title: "Introducing the External Sandbox Pattern for Secure AI Agent Code Execution"
slug: "introducing-the-external-sandbox-pattern-for-secure-ai-agent-code-execution"
description: "On November 17, 2026, a new project developed in collaboration with Prime Radiant introduced the external sandbox pattern. Under this pattern, code executed by an AI agent runs inside a dedicated..."
date: 2026-11-18T12:19:35+05:30
tags: [AIAgents, Sandboxing, PrimeRadiant, SecureCode]
categories: ["AI", "AI Agents", "Cybersecurity", "Software Development"]
image: "https://static.simonwillison.net/static/2026/sandbox-proxy.png"
author: "Shoubhik Banerjee"
draft: false
---

# Introducing the External Sandbox Pattern for Secure AI Agent Code Execution

On November 17, 2026, a new project developed in collaboration with Prime Radiant introduced the external sandbox pattern. Under this pattern, code executed by an AI agent runs inside a dedicated sandbox, while the agent itself resides outside of that sandbox.

## 🔍 Overview
The external sandbox pattern separates the AI agent from the environment where its executed code runs. To demonstrate this pattern, three sandbox server implementations have been released. These sandboxes can be configured to receive API calls from AI agents such as Pi, Claude Code, or Codex whenever they need to execute code.

## ⚙️ Key features
* **Unified API**: Each implementation offers the same localhost API.
* **Allow-list Proxy**: An optional HTTP/HTTPS proxy to control exactly which hosts the agent's code is allowed to communicate with.
* **Credential Replacement**: A mechanism that allows the agent's code to make authenticated API calls without sharing secret credentials directly with the agent.

## 🧩 Sandbox implementations

| Implementation | Description |
| :--- | :--- |
| `external-sandbox-v86` | A Node.js server that uses v86 to run Alpine Linux inside WebAssembly. |
| `external-sandbox-container` | A Python web server that runs the sandbox in Alpine Linux inside an Apple Containers instance. |
| `external-sandbox-quicksand` | A Python web server that uses Microsoft's Quicksand sandboxing library to bundle QEMU and Alpine Linux in a Python package. |

#AIAgents #Sandboxing #PrimeRadiant #SecureCode

---

*Source: [External sandboxes for coding agents](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/)*
