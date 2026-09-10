---
title: "Pizza Bot Released as an Open Source, Self-Hosted AI Agent Application"
slug: "pizza-bot-released-as-an-open-source-self-hosted-ai-agent-application"
description: "Today marks the release of Pizza Bot, an open source application that runs AI agents in the background and provides them with an inbox interface. Designed to keep agents working without constant..."
date: 2026-09-10T22:04:27+05:30
tags: [PizzaBot, AIAgents, OpenSource, SelfHosted]
categories: ["AI", "AI Agents", "Software Development", "Productivity Tools"]
image: "https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/09/pizza-bot-featured-1144x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# Pizza Bot Released as an Open Source, Self-Hosted AI Agent Application

Today marks the release of Pizza Bot, an open source application that runs AI agents in the background and provides them with an inbox interface. Designed to keep agents working without constant human monitoring, Pizza Bot ensures that background agents return to you only when they are finished or when they get stuck, rather than before.

## 🔍 Overview

Pizza Bot is a finished application built for people who need daily work done rather than for writing software. The tool originally began inside Amazon, where more than 2,000 employees utilized earlier versions for various tasks, including:
* Meeting preparation and follow-ups
* Email drafting
* Slack summaries
* CRM logging
* Day prioritization
* Web research

A small team rebuilt the application from the ground up as an open source project, a process made practical through the use of coding agents.

## 🧩 How It Works

Pizza Bot operates on an inbox model to manage background tasks. Users can initiate a task manually, set it on a schedule, or allow a webhook to start it. The interface organizes tasks using specific folders and panels:

| Folder / Panel | Description |
| :--- | :--- |
| **Unread** | Completed work that you have not yet reviewed. |
| **Action** | Paused work waiting on your approval or your answer. |
| **Activity** | Shows work the main agent handed to a specialist, including that specialist's own transcript. |

To expand capabilities, Pizza Bot connects to Model Context Protocol (MCP) servers for tools, and it works with Agent Skills, which is the Markdown convention introduced by Anthropic for packaging specialist knowledge.

## ⚙️ Key Details

Pizza Bot is structured as both a server and a client:
* **The Server:** Runs the agent, owns its state, and answers over HTTP.
* **The Client:** Can be the Electron desktop application, a web browser, or a terminal.

The desktop application wraps both components, starting its own local server and connecting to it. Because the agent's work lives on the server, a run keeps going when you close the thread, reload the page, or switch devices. A client that reconnects will catch up on what it missed.

If you host the server on an always-on machine or inside a container, you can access the same threads from a laptop, phone, or terminal. Conversely, quitting the desktop application stops its local server and ends its current runs. However, because runs are checkpointed as they go, you only lose the step currently in flight rather than the entire thread.

## 🛡️ Security and Compatibility

Pizza Bot is self-hosted, features no telemetry, and runs locally. Everything it stores remains in a folder you own, and the application only listens on your own machine unless you configure it otherwise. Nothing leaves your machine unless you explicitly send it there.

It allows you to choose your own model provider, with support for:
* Anthropic
* Amazon Bedrock
* Google Gemini
* OpenAI
* OpenRouter
* Local models through Ollama

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/09/pizza-bot-figure-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/09/pizza-bot-figure-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/09/pizza-bot-figure-3.png)

#PizzaBot #AIAgents #OpenSource #SelfHosted

---

*Source: [Introducing Pizza Bot, an open source inbox for AI agents that work in the background | Amazon Web Services](https://aws.amazon.com/blogs/opensource/introducing-pizza-bot-an-open-source-inbox-for-ai-agents-that-work-in-the-background/)*
