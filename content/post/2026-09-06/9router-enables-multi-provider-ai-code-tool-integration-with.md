---
title: "9router enables multi‑provider AI code tool integration with token savings"
description: "A new open‑source router called **9router** lets developers connect a wide range of AI code tools—such as Claude Code, Codex, Cursor, Cline, GitHub Copilot, and Antigravity—to more than 40 AI..."
date: 2026-09-06T22:07:38+05:30
tags: [AIcode, 9router, tokenSaving, multiProvider]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/8282593?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# 9router enables multi‑provider AI code tool integration with token savings

A new open‑source router called **9router** lets developers connect a wide range of AI code tools—such as Claude Code, Codex, Cursor, Cline, GitHub Copilot, and Antigravity—to more than 40 AI providers and over 100 models.

## 🔗 Overview
- Connects Claude Code, Codex, Cursor, Cline, Copilot, Antigravity, OpenCode, OpenClaw and other CLI tools to 40+ providers.
- Supports subscription, cheap, and free tiers across many models.
- Provides a local dashboard at `http://localhost:20128` and an OpenAI‑compatible API endpoint.

## ⚙️ How it works
- **RTK Token Saver**: auto‑compresses `tool_result` content, saving 20‑40 % tokens per request.
- **Auto fallback**: switches from subscription to cheap to free models without downtime.
- **Multi‑account**: round‑robin distribution between accounts per provider.
- **Format translation**: converts prompts between OpenAI and Claude formats.
- **Quota tracking** and **auto token refresh** keep usage smooth.

## 📦 Tiered model access
| Tier | Cost | Included tools / models |
|------|------|--------------------------|
| 1 – Subscription | Paid | Claude Code, Codex, GitHub Copilot |
| 2 – Cheap | $0.6 / 1M tokens (GLM) or $0.2 / 1M tokens (MiniMax) |
| 3 – Free | Free credits (Kiro, OpenCode Free, Vertex $300 credits) |

## 🚀 Availability
- Install with `npm install -g 9router`.
- Dashboard opens at `http://localhost:20128/dashboard`.
- API endpoint: `http://localhost:20128/v1` (OpenAI‑compatible).
- Example model reference: `kr/claude-sonnet-4.5`.
- Connect free providers such as Kiro AI (≈50 credits/month) or OpenCode Free (no auth).

## 💡 Why it matters
- Reduces token usage by 20‑40 % per request.
- Guarantees zero‑downtime access by falling back to cheaper or free models.
- Gives developers a single point of control for dozens of AI code assistants.


#AIcode #9router #tokenSaving #multiProvider

---

*Source: [decolua/9router](https://github.com/decolua/9router)*
