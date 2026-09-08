---
title: "Enhanced ChatGPT Clone Introduces Advanced Agent Controls and Multi-Model Integration"
slug: "enhanced-chatgpt-clone-introduces-advanced-agent-controls-and-multi-model-integration"
description: "An enhanced ChatGPT clone has been released as an open-source project for self-hosting, featuring extensive agent orchestration, multi-model support, and advanced security integrations."
date: 2026-09-09T00:51:34+05:30
tags: [AIagents, OpenSource, LLM, ChatGPTClone]
categories: ["AI Agents", "Software Development", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/110412045?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Enhanced ChatGPT Clone Introduces Advanced Agent Controls and Multi-Model Integration

An enhanced ChatGPT clone has been released as an open-source project for self-hosting, featuring extensive agent orchestration, multi-model support, and advanced security integrations.

## ⚙️ Key Details

### Model and Integration Support
The platform supports a wide array of models and APIs, including:
* **Models:** GPT-5, o1, Gemini, Mistral, Claude, and GPT-5.6 with Responses reasoning controls.
* **Providers:** OpenAI, Anthropic, AWS, Azure, Groq, Vertex AI, and OpenRouter.
* **Tooling:** MCP, langchain, DALL-E-3, OpenAPI Actions, and Functions.

### Agent Capabilities
* **Run Control:** Users can interrupt Agents before visible text appears, steer runs using files and quoted excerpts, queue follow-ups, and recover partial work via "Keep going" or "Answer now."
* **Activity Tracking:** Includes optional generated labels for reasoning and tool work, phase cards, current reasoning direction indicators, and multi-step phase summaries.
* **Human-in-the-Loop:** Support for streaming up to four related questions and pausing for input or tool approval.
* **Automation:** Authenticated Agent Events support bound child actors, per-actor mailboxes, event batching, and automatic detached Actions.
* **Subagent Management:** Features branch-aware child turns, the ability to continue completed child chats, and automatic waking of saved parent Agents.

### Tooling and Workflows
* **Unified Agent Builder:** A single marketplace to configure Skills, MCP, Code Interpreter, orchestration, and programmatic tool calling.
* **Code Interpreter:** Includes sandbox images returned as artifacts and experimental stateful sessions with guarded file-write and command permissions.
* **Background Tools:** MCP, Plugin, Action, and Code Interpreter tools can run while an Agent continues working.
* **Scheduled Chats:** Experimental support for running saved Agents via custom cron or presets with selectable time zones.

### System Features

| Feature | Description |
| :--- | :--- |
| **Memory** | Optionally isolated memory with adaptive context fading and token/cost tracking |
| **Web Search** | Keyless search via Keenable; richer controls for SearXNG and Tavily with SSRF protection |
| **Sharing** | Stable shared links for personal copies; exports for Mermaid, PowerPoint, and shell scripts |
| **Navigation** | Searchable conversation titles and message contents; pinned chats and project management |
| **Text Handling** | Long pastes become editable attachments that can move back into the composer |

## 🔒 Security and Authentication

Deployments are hardened with the following:
* Default HTTP security headers and opt-in nonce CSP.
* Per-user Code Interpreter JWTs and stable SAML identity binding.
* Live-session OpenID token refresh.
* Authenticated local images.

## 🚀 Availability

The project is open-source for self-hosting and can be deployed on Railway.

#AIagents #OpenSource #LLM #ChatGPTClone

---

*Source: [danny-avila/LibreChat](https://github.com/danny-avila/LibreChat)*
