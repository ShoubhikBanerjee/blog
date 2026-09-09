---
title: "Codex Pooler launches as a self-hosted gateway for Codex-compatible agents"
slug: "codex-pooler-launches-as-a-self-hosted-gateway-for-codex-compatible-agents"
description: "Codex Pooler has been introduced as a self-hosted gateway designed for running Codex-compatible agents, tools, and automation through stable Pool API keys."
date: 2026-09-09T18:04:04+05:30
tags: [CodexPooler, DeveloperTools, AIInfrastructure, SelfHosted]
categories: ["AI", "Developer Tools", "AI Infrastructure", "Access Control"]
image: "https://avatars.githubusercontent.com/u/188930?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Codex Pooler launches as a self-hosted gateway for Codex-compatible agents

Codex Pooler has been introduced as a self-hosted gateway designed for running Codex-compatible agents, tools, and automation through stable Pool API keys.

## 🔍 Overview

Codex Pooler connects clients to upstream accounts while maintaining a stable access key interface. The gateway supports different configurations depending on the number of accounts:
* **Single upstream Codex account:** Provides credential isolation, client normalization, metadata-only operations, and saved reset visibility.
* **Multiple upstream accounts:** Added to provide shared capacity and routing across eligible accounts.

## 🧩 How it works

Clients send familiar Codex backend or OpenAI-compatible requests to the gateway. While upstream assignments, lifecycle states, reset policies, and capacity change behind the scenes, the external Pool key remains stable.

When a request is made, Codex Pooler selects an eligible account based on the following criteria:
* Model support
* Quota evidence
* Limits
* Session continuity
* Routing policy
* Health

## ⚙️ Key details

Operators and administrators are provided with specific control surfaces to manage their environments securely.

### Administration Roles
* **Instance owners:** Maintain the global administration surface.
* **Instance admins:** Work exclusively with their assigned Pools.

### Operator Management
Operators get a single centralized place to manage Pools, accounts, API keys, saved resets, routing, request accounting, audit logs, and health. This management is conducted without storing:
* Prompts
* Files
* Audio
* Images
* Bearer tokens
* Raw Codex secrets

#CodexPooler #DeveloperTools #AIInfrastructure #SelfHosted

---

*Source: [icoretech/codex-pooler](https://github.com/icoretech/codex-pooler)*
