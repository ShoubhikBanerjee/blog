---
title: "DashClaw introduces real‑time guard and approval ledger for AI agents"
slug: "dashclaw-introduces-realtime-guard-and-approval-ledger-for-ai-agents"
description: "DashClaw adds a real‑time guard that intercepts potentially destructive or costly actions from AI agents such as OpenClaw, Hermes, Claude Code, and Codex."
date: 2026-09-09T22:05:26+05:30
tags: [AIagents, Security, Compliance, Automation]
categories: ["AI", "Artificial Intelligence", "AI Safety", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/128239567?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# DashClaw introduces real‑time guard and approval ledger for AI agents

DashClaw adds a real‑time guard that intercepts potentially destructive or costly actions from AI agents such as OpenClaw, Hermes, Claude Code, and Codex.

## 🔍 Overview
- "With a supported enforcement integration, when your AI agent (OpenClaw, Hermes, Claude Code, Codex) tries something destructive or expensive, DashClaw catches it before it runs and asks you first, even when you are not at the keyboard."

## 🛡️ Enforcement
- "The Claude Code, Codex, and Hermes hooks, the OpenClaw gateway, and `dashclaw_invoke` can cancel a blocked call before execution."
- "Bare SDK, API, and ordinary MCP integrations are cooperative: the caller must honor the verdict."

## 📋 Approval Workflow
- "Resolve from the `/approvals` inbox, the CLI, a phone PWA, Telegram, or Discord."
- "Every pending item leads with one sentence for what the command actually does, flags what cannot be undone, and warns when a file holds credentials."
- "The exact command is always shown underneath."
- "Preview the target, lease, and matching pending items before creating a scoped standing grant."
- "The UI resolves eligible items through the normal approval path and reports partial failures."
- "High‑risk, ungrantable, expired, or self‑approved sources are rejected."
- "Standing grants remain visible and revocable in the inbox."

## 📜 Ledger & Auditing
- "Every decision lands in a signed ledger."
- "Decision records, Ed25519 receipts where issued, and signed exports support later review."
- "A receipt verifies its signed contents, not that an external effect happened."
- "Authenticated identity and action‑payload signing are shown separately."
- "Each action carries the agent's stated confidence — declared on the guard call, before the act, so it is a prediction and not a postscript — and the ledger scores it against the reported outcome, so an overconfident agent shows up as a number on /decisions, not as a surprise."

## ⚙️ Configuration & Diagnostics
- "The API key lands in `~/.dashclaw/instance.json`; verify with `GET http://localhost:3000/api/health` and `npx dashclaw doctor`."
- "Setup distinguishes stale, broken, and unavailable evidence and shows measured runtime versions and hook fingerprints as client‑reported diagnostics, not attestation."
- "Prompt‑injection scanning on by default."

## 🎚️ Policy Tuning
- "Your approve/deny verdicts tune how often it interrupts, with a proven cap on false interruptions instead of a guessed threshold."
- "How much your agent ships without a human looking is set by policy thresholds and checks, not by wording."
- "A probe tests whether a synthetic held action executes through the installed hook path."


#AIagents #Security #Compliance #Automation

---

*Source: [ucsandman/DashClaw](https://github.com/ucsandman/DashClaw)*
