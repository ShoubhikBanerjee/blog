---
title: "Codex Pooler Introduced as Self-Hosted Gateway for Codex-Compatible Agents"
slug: "codex-pooler-introduced-as-self-hosted-gateway-for-codex-compatible-agents"
description: "Codex Pooler is a self-hosted gateway designed to run Codex-compatible agents, tools, and automation using stable Pool API keys."
date: 2026-09-17T00:45:10+05:30
tags: [Codex, API, AIagents, SelfHosted]
categories: ["AI", "AI Agents", "Software Infrastructure", "API Management"]
image: "https://avatars.githubusercontent.com/u/188930?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Codex Pooler Introduced as Self-Hosted Gateway for Codex-Compatible Agents

Codex Pooler is a self-hosted gateway designed to run Codex-compatible agents, tools, and automation using stable Pool API keys.

## 🔍 Overview
Codex Pooler allows operators to manage pools, accounts, API keys, saved resets, routing, request accounting, audit logs, and health. The system is designed so that operators do not store raw Codex secrets, bearer tokens, prompts, files, audio, or images.

## 🧩 How it works
Clients send OpenAI-compatible or Codex backend requests to the Codex Pooler. The system then selects an eligible account based on the following criteria:
* Model support
* Quota evidence
* Limits
* Session continuity
* Routing policy
* Health

## ⚙️ Key details

| Feature | Description |
| :--- | :--- |
| Stable Pool API keys | Provides clients with one credential regardless of whether the Pool has one or several upstream accounts, avoiding the distribution of raw Codex account material. |
| Eligibility-aware routing | Routes requests to accounts with matching health, session state, Pool policy, usable quota evidence, and compatible model support. |
| Codex backend compatibility | Allows Codex-compatible clients to point at Codex Pooler while maintaining usage, compacting, and responses. |

## 💡 Why it matters
* **Credential Isolation:** It works with one upstream Codex account for client normalization, metadata-only operations, saved reset visibility, and credential isolation.
* **Scalability:** Additional accounts can be added for routing and shared capacity across eligible accounts.
* **Stability:** The Pool key remains stable even when capacity, reset policy, lifecycle state, and upstream assignments change.
* **Administrative Control:** Instance owners maintain the global administration surface, while instance admins are restricted to their assigned Pools.

#Codex #API #AIagents #SelfHosted

---

*Source: [icoretech/codex-pooler](https://github.com/icoretech/codex-pooler)*
