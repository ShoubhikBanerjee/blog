---
title: "claude-tap Offers Local Tracing for AI Coding Agents"
slug: "claude-tap-offers-local-tracing-for-ai-coding-agents"
description: "claude-tap is a local proxy and trace viewer for AI coding agents, letting users inspect API traffic and agent context. Its workflow supports reviewing individual requests, comparing changes between..."
date: 2026-11-17T12:12:52+05:30
tags: [AIAgents, CodingAgents, DeveloperTools, APIDebugging]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Developer Tools", "Software Development"]
image: "https://avatars.githubusercontent.com/u/34056481?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# claude-tap Offers Local Tracing for AI Coding Agents

claude-tap is a local proxy and trace viewer for AI coding agents, letting users inspect API traffic and agent context. Its workflow supports reviewing individual requests, comparing changes between turns, and exporting trace sessions as standalone HTML files.

## 🔍 What it captures

The viewer can show:

- System prompts and conversation history
- Tool schemas, tool calls, and tool results
- Reconstructed streaming responses
- Token usage
- Diffs between adjacent requests

Users can run a CLI through claude-tap or listen to local app transcripts, then open an agent run and inspect its requests to see how context changes between turns. The viewer has light and dark modes.

## 🧩 Supported clients

The evidence lists support for these tools and clients:

- Claude Code, Codex CLI, Codex App, and Gemini CLI
- Grok Build CLI, DeepSeek Harness, Kimi CLI, and MiMo Code
- OpenCode, OpenClaw, Pi, and Hermes Agent
- Cursor CLI, Qoder CLI, and CodeBuddy CLI

## 🛠️ Traces and prompt snapshots

Each run writes a local trace session that can be exported as a self-contained HTML viewer for review or archiving. No hosted dashboard is required.

Phistory archives versioned system-prompt snapshots from agent CLIs, including Claude Code, Codex, Kimi, OpenCode, and Pi. It uses claude-tap’s capture-only prompt export to preserve raw HTTP trace evidence and create snapshots for comparison in a prompt diff viewer.

## 🔐 Data handling

Common authentication headers are replaced with `***` before recording, without retaining credential prefixes. Upstream requests receive the original headers. The stated redaction does not cover request or response bodies, URLs, or diagnostic text.

#AIAgents #CodingAgents #DeveloperTools #APIDebugging

---

*Source: [liaohch3/claude-tap](https://github.com/liaohch3/claude-tap)*
