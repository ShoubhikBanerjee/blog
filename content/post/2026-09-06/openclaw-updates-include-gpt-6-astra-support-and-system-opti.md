---
title: "OpenClaw Updates Include GPT-6 Astra Support and System Optimizations"
description: "OpenClaw has released an update introducing support for GPT-6 Astra, expanded plugin capabilities, and several performance and stability improvements across macOS, iOS, and Android platforms."
date: 2026-09-06T22:07:38+05:30
tags: [OpenClaw, GPTo6Astra, AIagents, SoftwareUpdate]
categories: [AI]
image: "https://opengraph.githubassets.com/f26274264252b953a463ed0b2bb938b994be39c6ab83f6ec24afdb5e21b7fc25/openclaw/openclaw"
author: "Shoubhik Banerjee"
draft: false
---

# OpenClaw Updates Include GPT-6 Astra Support and System Optimizations

OpenClaw has released an update introducing support for GPT-6 Astra, expanded plugin capabilities, and several performance and stability improvements across macOS, iOS, and Android platforms.

## 🚀 New Model Support

Support for **GPT-6 Astra** is now available via OpenAI API-key profiles or eligible ChatGPT/Codex accounts. Key capabilities include:

* **Inputs and Outputs**: Support for text and image input, Responses tool calls, and reasoning controls.
* **Async Tools and Steering**: On OpenAI Platform API-key routes using the built-in OpenClaw runtime and official Responses endpoint, the system can run direct function tools asynchronously and steer active responses over cached WebSockets.
* **Reasoning**: Includes `/think ultra` orchestration for OpenClaw and native Codex runtimes, retention of configured Azure deployment capabilities, and correct reasoning and sampling settings when catalog metadata is absent.
* **Continuations**: Request prefixes are retained when changing reasoning effort under documented configuration, and steering history and encrypted reasoning are kept through continuations.

## ⚙️ Key Details

### System Performance and Stability
* **Responsiveness**: Chat, dashboards, and session interactions remain responsive during long transcript and disk usage processing via direct dashboard lookup and durable history reads outside the Gateway event loop.
* **Recovery**: Replies (active, queued, and delegated) now survive Gateway restarts without completed replies discarding other recovery markers. Continuation instructions are maintained through retry attempts and compaction.
* **Updates**: Automatic updates now preserve active settings, enabled skills, and default-agent ownership. Gateway restarts after Git updates are restored with actionable recovery guidance.
* **Backups**: Git backups now preserve complete text containing embedded NUL characters. The system supports Nix-managed config and credential links and rejects corrupt archive headers.
* **Live Settings**: Settings for agents, models, tools, channels, browsers, nodes, access, and terminals can be applied through their running owners without a Gateway restart.

### Interface and Integration
* **Dashboards**: Users can browse saved dashboards in a gallery, swap chat and dashboard views, and position panels left, right, or below. Widget input is kept when hiding and reopening panels.
* **Plugins**: Plugins can now package icons at `assets/icon.png` for local loading. An experimental Custom plugin UI (enabled via Settings → Labs) allows plugins to contribute Control UI pages, panels, session actions, or customize the workspace and composer.
* **Platform Integration**: 
    * **macOS**: Includes simplified approval panels for commands, nodes, and devices, and personal Cloudflare Access browser sign-in to connect saved Gateways.
    * **iOS/macOS**: Native text copying for messages and direct copying of code blocks on iOS.
    * **Slack**: Support for Block Kit layouts in proactive replies and native session controls including a Stop button, synchronized titles, and processing/approval status.
    * **Discord**: Occupancy-driven, listen-only meeting capture with automatic notes and a Control UI Meetings page.
    * **Apple Watch**: Experimental standalone Talk with Gateway-owned tools and transcripts (requires UDP connectivity).

### Agent and Session Management
| Feature | Description |
| :--- | :--- |
| **Swarm** | Enabled by default to orchestrate concurrent sub-agents with live progress; preserves explicit opt-outs and tool restrictions. |
| **Connected Accounts** | Add provider accounts via CLI or Settings to choose accounts for new or existing chats. |
| **Cross-agent Access** | Session tools default to all-session visibility; ordinary agent-to-agent access is enabled. |
| **Teammates** | Mention authorized people from the composer to send temporary Inbox entries. |
| **Device Monitoring** | The Devices page shows resource meters and capability chips, including native iOS CPU/memory and Android memory/disk reporting. |

#OpenClaw #GPTo6Astra #AIagents #SoftwareUpdate

---

*Source: [Releases · openclaw/openclaw](https://github.com/openclaw/openclaw/releases)*
