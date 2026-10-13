---
title: "Pre‑commit Hook Enforces Diagnostics Library for AI Agents"
slug: "precommit-hook-enforces-diagnostics-library-for-ai-agents"
description: "On 13 October 2026 a developer introduced a pre‑commit hook to force AI agents to use a diagnostics library, tightening observability and preventing drift."
date: 2026-10-13T22:07:53+05:30
tags: [AIagents, DevOps, Observability]
categories: ["AI", "Artificial Intelligence", "Software Engineering", "Machine Learning"]
author: "Shoubhik Banerjee"
draft: false
---

# Pre‑commit Hook Enforces Diagnostics Library for AI Agents

On 13 October 2026 a developer introduced a pre‑commit hook to force AI agents to use a diagnostics library, tightening observability and preventing drift.

## 🔍 Overview
- "If the agent isn't using my diagnostics library, I could introspect and update AGENTS.md, but there's still a delta, and it'll drift."

## 🛠️ How it works
- Instead, a pre‑commit hook is written that scans the **git diff** for direct calls to observability modules that bypass the diagnostics module.  
- When such a call is detected, the hook **fails the commit** and injects a prompt telling the agent to use the diagnostics library.

## ✅ Results
- "Boom: fail the commit, inject a prompt telling the agent to use the diagnostics library."
- After the change, the author notes: "All of a sudden it's ten out of ten."

## 🗣️ Commentary
- "— Geoffrey Huntley, nobody should type code by hand anymore."
- The post concludes with: "here's what's left."


#AIagents #DevOps #Observability

---

*Source: [A quote from Geoffrey Huntley](https://simonwillison.net/2026/Oct/13/geoffrey-huntley/)*
