---
title: "ClawGod: Runtime Patch for Privacy and Features in Claude Code"
slug: "clawgod-runtime-patch-for-privacy-and-features-in-claude-code"
description: "ClawGod is a runtime patch applied to the official Claude Code. It is not a third-party client but a layer applied on top of the existing application that continues to be supported with each version..."
date: 2026-11-17T22:09:21+05:30
tags: [ClaudeCode, ClawGod, AIAgents, DevTools, Privacy]
categories: ["AI", "AI Development Tools", "Developer Productivity", "Security & Privacy", "Software Patching"]
image: "https://avatars.githubusercontent.com/u/19362246?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ClawGod: Runtime Patch for Privacy and Features in Claude Code

ClawGod is a runtime patch applied to the official Claude Code. It is not a third-party client but a layer applied on top of the existing application that continues to be supported with each version update.

## 🔍 Overview
As Claude Code updates, ClawGod automatically re-extracts and re-patches against the new version on the next launch. This ensures compatibility with any version of the official tool. The patch is designed to enhance functionality and modify specific behaviors, such as enabling "God mode" and implementing privacy protections that are enabled by default.

## 🧩 How it works
The tool operates by modifying internal logic at runtime. A key aspect of its functionality is the neutralization of known location and proxy signals embedded in prompts. For instance, the "Date String" feature addresses a system prompt encoding where user location was inferred via Unicode apostrophe variants and date separators; ClawGod patches this to always use ASCII apostrophes and unmodified date formats. Additionally, the "Geo-Detection Probe" is patched to always return null, preventing client-side detection based on timezone, proxy hostnames, or vendor keywords.

## ⚙️ Key details
ClawGod introduces a wide range of features and overrides, including:

*   **Internal User Mode**: Access to 24+ hidden commands (e.g., `/share`, `/teleport`, `/issue`), debug logging, and API request dumps.
*   **GrowthBook Overrides**: The ability to override any feature flag via a config file.
*   **Agent Teams**: Multi-agent swarm collaboration without requiring flags.
*   **Computer Use**: Screen control on macOS without a Max/Pro subscription.
*   **Auto-mode**: Unlocks auto-mode for third-party API users by removing the `firstParty` gate.
*   **Classifier Tuning**: Tunable parameters for the auto-mode classifier, including timeout, model, and retries.
*   **Ultraplan & Ultrareview**: Multi-agent planning and automated bug hunting via Claude Code Remote.

## 🛡️ Privacy and Security
Since v2.3.0, ClawGod blocks the automatic collection of Git origin and environment metadata for the `x-claude-code-wiggly-dove` header. The patch ensures the shared eligibility gate returns false before the collector runs, preventing the reading of Git origin or other environment metadata. Other security features include:

*   **CYBER_RISK_INSTRUCTION**: Refusal mechanisms for security testing and exploits.
*   **URL Restriction**: Instructions to never generate or guess URLs.
*   **Cautious Actions**: Forced confirmation before destructive operations.
*   **Enterprise Remote Settings**: Organization-managed settings for forced permission rules and version pinning, which can be disabled via `CLAWGOD_FEATURE_REMOTE_SETTINGS=false`.

## 🚀 Availability
ClawGod is available via installation scripts for different operating systems:

*   **Linux/macOS**: `curl -fsSL https://github.com/0Chencc/clawgod/releases/latest/download/install.sh | bash`
*   **Windows**: `irm https://github.com/0Chencc/clawgod/releases/latest/download/install.ps1 | iex`

#ClaudeCode #ClawGod #AIAgents #DevTools #Privacy

---

*Source: [0Chencc/clawgod](https://github.com/0Chencc/clawgod)*
