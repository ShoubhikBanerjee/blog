---
title: "GitHub develops Agent Host Protocol to enable continuous multi-device AI sessions"
slug: "github-develops-agent-host-protocol-to-enable-continuous-multi-device-ai-sessions"
description: "The newly developed Agent Host Protocol (AHP) is an open standard designed to keep AI agent sessions accessible and continuous across editors, applications, mobile phones, and the cloud. As models..."
date: 2026-11-18T18:09:03+05:30
tags: [AHP, GitHubCopilot, AIAgents, VSCode, DeveloperTools]
categories: ["AI", "AI Agents", "Software Development", "Cloud Computing"]
image: "https://github.blog/wp-content/uploads/2026/11/agents-everywhere.png"
author: "Shoubhik Banerjee"
draft: false
---

# GitHub develops Agent Host Protocol to enable continuous multi-device AI sessions

The newly developed Agent Host Protocol (AHP) is an open standard designed to keep AI agent sessions accessible and continuous across editors, applications, mobile phones, and the cloud. As models become capable of working independently for hours or days, AHP ensures that developers can check in on their progress from any device, allowing sessions to persist even when users switch devices or close windows.

## 🔍 Overview
In the past, GitHub Copilot was built as a VS Code extension, tying the lifetime of agents directly to the VS Code editor window. Closing the window, restarting VS Code for an update, or connecting to a remote machine would terminate the agent session or reset the extension host. To resolve this limitation and allow developers to pull agents into their custom workflows, editors, terminals, or mobile apps, the Agent Host Protocol provides a standard, independently versioned language. This shared protocol ensures every client sees the same agents, history, and state without requiring bespoke, one-off integrations.

## 🧩 How it works
To handle multi-client interactions seamlessly, the Agent Host Protocol is designed with several core architectural features:

- **URI-identified Channels**: This is the coarsest unit of functionality in the protocol. Every server must implement the root, session, and chat channels, and can optionally implement other channels such as terminal support, Model Context Protocol (MCP) additions, or OpenTelemetry (OTel) reporting.
- **Reducer-Based State Object**: Inside each channel, a reducer-based state object drives client-side logic. The server acts as the arbiter of this state, while the client sends a sequence of actions that either mutate the state or trigger side effects.
- **Network Resiliency**: Under poor network conditions, reconnection and replay are simplified. Clients can send all queued actions and present a loading state while waiting for the server to reconcile and acknowledge the actions.
- **Minimal Core**: To make implementation straightforward on custom clients and servers, the core protocol is kept minimal while allowing extensive features to be built on top.

## ⚙️ Key details

- **Focus on Interaction, Not Behavior**: Unlike the Language Server Protocol (LSP) or Debug Adapter Protocol (DAP), AHP avoids encoding how agents work, focusing solely on how users interact with them to accommodate rapidly evolving agent models.
- **Rebuilding the VS Code Stack**: Adopting AHP in VS Code required building a new harness and agentic stack underneath it. The existing Copilot Chat extension had grown for over three years to more than 400,000 lines of TypeScript (excluding tests) and was heavily dependent on the VS Code window lifecycle and APIs that are unavailable in a standalone agent host process.

![figure](https://github.blog/wp-content/uploads/2026/11/session-across-surfaces.png?resize=1024%2C512)

![figure](https://github.blog/wp-content/uploads/2026/11/ahp-protocol-state.png?resize=1024%2C512)

![figure](https://github.blog/wp-content/uploads/2026/11/agents-everywhere.png?resize=1536%2C850)

#AHP #GitHubCopilot #AIAgents #VSCode #DeveloperTools

---

*Source: [Building the Agent Host Protocol for sessions that continue across devices](https://github.blog/engineering/engineering-principles/building-the-agent-host-protocol-for-sessions-that-continue-across-devices/)*
