---
title: "Claude Code updates 2.1.288 and 2.1.289 enhance security and subagent resilience"
slug: "claude-code-updates-2-1-288-and-2-1-289-enhance-security-and-subagent-resilience"
description: "Claude Code has been updated to versions 2.1.288 and 2.1.289, introducing security patches for sandbox execution and improved handling of subagent sessions during network interruptions."
date: 2026-10-04T22:04:46+05:30
tags: [ClaudeCode, AIagents, SoftwareDevelopment]
categories: ["AI", "AI Agents", "Software Engineering", "Cybersecurity"]
image: "https://ai-tldr.dev/og-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Claude Code updates 2.1.288 and 2.1.289 enhance security and subagent resilience

Claude Code has been updated to versions 2.1.288 and 2.1.289, introducing security patches for sandbox execution and improved handling of subagent sessions during network interruptions.

## 🔍 Overview
The latest releases of Claude Code focus on hardening bash command security and ensuring that automated coding sessions can recover from API timeouts without losing progress.

## ⚙️ Key details
* **Security Hardening:** Version 2.1.289 closes gaps where Bash "deny" and "ask" rules could be skipped, such as those occurring behind an environment variable prefix under sandbox auto-allow configurations.
* **Session Resilience:** Version 2.1.288 allows headless sessions and subagents to continue from a partial reply following an API timeout.
* **Plugin Support:** The update adds `agent.spawn` for plugin teammates.
* **Stability Improvements:** These versions include fixes for many mod and plugin crashes.

## 📊 Update Summary
| Version | Key Changes |
| :--- | :--- |
| 2.1.288 | Enables subagents and headless sessions to resume from partial replies after timeouts. |
| 2.1.289 | Prevents security rule bypasses in sandboxes and adds `agent.spawn` functionality. |

#ClaudeCode #AIagents #SoftwareDevelopment

---

*Source: [New AI Releases Daily — Models, Tools & Papers | AI/TLDR](https://ai-tldr.dev/)*
