---
title: "OpenHands Introduces Agent Canvas for Coding Agents and Automations"
slug: "openhands-introduces-agent-canvas-for-coding-agents-and-automations"
description: "OpenHands has released Agent Canvas, a self-hosted developer control center designed for managing coding agents and automations across various backends."
date: 2026-09-17T00:50:10+05:30
tags: [OpenHands, AIagents, CodingAgents, DeveloperTools, Automation]
categories: ["AI", "AI Agents", "Software Development", "Automation"]
image: "https://avatars.githubusercontent.com/u/45487711?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenHands Introduces Agent Canvas for Coding Agents and Automations

OpenHands has released Agent Canvas, a self-hosted developer control center designed for managing coding agents and automations across various backends.

## 🔍 Overview
Agent Canvas allows developers to run coding agents—such as OpenHands, Claude Code, Codex, and Gemini—across local, remote, and cloud environments. It functions as a control center for starting conversations and automating tasks, such as decomposing GitHub issues into tasks or generating reports for Slack.

## 🧩 How it works
Agent Canvas utilizes the Agent-Client Protocol (ACP) to connect with agent backends. The system architecture follows a specific flow: SDK/Agent Server $\rightarrow$ OpenAPI contract $\rightarrow$ clients/typescript $\rightarrow$ Agent Canvas.

*   **Execution Environments:** Agents can run on a local machine, in Docker containers, on VMs, or within company infrastructure. 
*   **Workspaces:** Agents utilize either the local machine as a workspace or ephemeral workspaces in Kubernetes or Docker via the Agent Server.
*   **Automation:** The system supports scheduling and responding to webhook events to integrate with third-party services.

## ⚙️ Key details
The platform is supported by the OpenHands Software Agent SDK, which provides REST APIs and libraries in Python and TypeScript. This SDK is used for several types of tasks:

| Task Type | Example Use Case |
| :--- | :--- |
| One-off tasks | Building a README for a repository |
| Routine maintenance | Updating dependencies |
| Major tasks | Refactors and rewrites involving multiple agents |

## 🚀 Availability
OpenHands can be installed on laptops, dedicated computers like a Mac Mini, or cloud servers. Running on a cloud server allows agents to remain active when a local laptop is shut down and simplifies triggers from services like Datadog, GitHub, and Slack. Users can switch between local, remote, and cloud agents through the same Agent Canvas frontend.

#OpenHands #AIagents #CodingAgents #DeveloperTools #Automation

---

*Source: [n8n-io/n8n](https://github.com/n8n-io/n8n)*
*Source: [langgenius/dify](https://github.com/langgenius/dify)*
*Source: [vstorm-co/full-stack-ai-agent-template](https://github.com/vstorm-co/full-stack-ai-agent-template)*
*Source: [OpenHands/OpenHands](https://github.com/OpenHands/OpenHands)*
*Source: [OpenHands/software-agent-sdk](https://github.com/OpenHands/software-agent-sdk)*
