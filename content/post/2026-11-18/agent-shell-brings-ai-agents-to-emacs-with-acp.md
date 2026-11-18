---
title: "agent-shell brings AI agents to Emacs with ACP"
slug: "agent-shell-brings-ai-agents-to-emacs-with-acp"
description: "agent-shell brings your favorite AI agents to Emacs, keeping you at home: familiar buffers and bindings, no terminal emulation. All powered by ACP, the Agent Client Protocol. Works with 24 agents..."
date: 2026-11-18T22:09:17+05:30
tags: [AIagents, Emacs, ACP, Sandstorm, agentshell]
categories: ["AI", "AI Agents", "Software Development", "Cloud Computing", "Emacs"]
image: "https://avatars.githubusercontent.com/u/8107219?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# agent-shell brings AI agents to Emacs with ACP

agent-shell brings your favorite AI agents to Emacs, keeping you at home: familiar buffers and bindings, no terminal emulation. All powered by ACP, the Agent Client Protocol. Works with 24 agents today, and any other that speaks ACP.

## 🔍 Overview
- agent-shell brings your favorite AI agents to Emacs, keeping you at home: familiar buffers and bindings, no terminal emulation.
- All powered by ACP, the Agent Client Protocol.
- Works with 24 agents today, and any other that speaks ACP.

## 🧩 How it works
- agent-shell relies on acp.el to communicate with agents via ACP (Agent Client Protocol).
- We now have a handful of additional packages to extend the agent-shell experience:
  - emacs-skills: Claude Agent skills for Emacs.
  - agent-shell-to-go: Interact with agent-shell sessions from your mobile or any other device via Slack.
  - agent-circus: Run AI coding agents in sandboxed Docker containers.
  - agent-shell-sidebar: A sidebar add-on for agent-shell.
  - agent-shell-bookmark: Bookmark support for agent-shell sessions.
  - agent-shell-workspace: Dedicated tab-bar workspace for managing multiple agent-shell sessions.
  - agent-shell-manager: Tabulated view and management of agent-shell buffers.
  - agent-review: Code review interface for agent-shell.
  - agent-shell-attention.el: Mode-line attention tracker for agent-shell.
  - agent-shell-knockknock: Notifications for agent-shell via knockknock.el.
  - agent-shell-notifications: Desktop notifications for agent-shell events.
  - meta-agent-shell: Multi-agent coordination system for agent-shell with inter-agent communication, task tracking, and project-level dispatching.

## ⚙️ Key details
- Run thousands of AI agent sandboxes on the cheapest machines.
- Sandstorm pauses idle sandboxes and snapshots them to disk, then restores them quickly when a request arrives, so one machine can hold far more sandboxes than it could run at once.
- It supports two sandbox backends, gVisor containers and Firecracker microVMs.
- Every sandbox has its own network namespace, and both backends can run in one fleet, each forming a resource pool of its own.
- The master serves a web console for viewing and managing sandboxes and scheduling across the fleet.
- Agents spend much of their time waiting.
- Sandstorm is designed around this behavior, with four sandbox tiers that progressively suspend idle sandboxes and quickly wake them when requests arrive.
- The master keeps desired state in SQLite and places sandboxes.
- Nodes join by address and pairing code, or dial out from behind NAT.
- A gateway on the sandbox's node wakes it and forwards the request.
- Nodes refuse new work when memory runs low, so SSH stays reachable.
- sandstormd serves as the master, node, and web console.
- gVisor and Firecracker each get their own optimizations.
- The master's web console shows sandbox states, tier transitions, and node headroom.
- Measured 2026-10-31, with requests from each node to its own gateway, so no network is in the path.
- gVisor needs no KVM and ran on six cloud nodes.
- Firecracker ran on one machine with KVM and one cloud VM under PVM.
- The hosts differ, so read each column on its own.
- Traffic is 40 sandboxes per node with a few getting most requests; about 12 fit awake on a gVisor node.
- p50 is 6-10 ms on gVisor, 7-50 ms on KVM.

## 🚀 Availability
- agent-shell is available with additional packages to extend its functionality.

## 💡 Why it matters
- agent-shell brings AI agents to Emacs, providing a familiar and integrated environment for AI interactions.
- The use of ACP allows for compatibility with a wide range of AI agents.
- The sandboxing and management features of Sandstorm enable efficient and scalable AI agent operations.

#AIagents #Emacs #ACP #Sandstorm #agent-shell

---

*Source: [xenodium/agent-shell](https://github.com/xenodium/agent-shell)*
*Source: [deeplethe/sandstorm](https://github.com/deeplethe/sandstorm)*
