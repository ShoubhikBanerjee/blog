---
title: "ThinkingBox Benchmark Reveals Gaps Between LLM Agent Tool Calls and Database State"
slug: "thinkingbox-benchmark-reveals-gaps-between-llm-agent-tool-calls-and-database-state"
description: "A joint Microsoft‑Hugging Face blog introduces **ThinkingBox**, a benchmark that runs LLM agents against isolated tool sessions, then grades the resulting backend database state and side effects."
date: 2026-10-04T22:04:46+05:30
tags: [ThinkingBox, LLM, AIAgents, Benchmark]
categories: ["AI", "Machine Learning", "AI Agents", "Evaluation", "Natural Language Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/64b8491203124195cd795cad/NStwJm1AafDELVsU4KGwS.png"
author: "Shoubhik Banerjee"
draft: false
---

# ThinkingBox Benchmark Reveals Gaps Between LLM Agent Tool Calls and Database State

A joint Microsoft‑Hugging Face blog introduces **ThinkingBox**, a benchmark that runs LLM agents against isolated tool sessions, then grades the resulting backend database state and side effects.

## 🔍 Overview
- The blog is co‑authored by Microsoft and Hugging Face, with thanks to Tommy Guy, Sergio Paniego, and former interns Zhuochun Li, Ali Keramati, and Youngmin Ko.
- Figure 1 shows the workflow: an agent interacts with MCP tool sessions, and a grader checks the terminal backend state and side effects.

## 🧩 How it works
- Each of the 507 stateful business workflows is executed 20 times from an identical clean backend.
- Agents invoke tools (e.g., order lookup, tracking, policy search) and produce final responses.
- An **AI grader** examines the **terminal database state** rather than just the sequence of tool calls.
- Example: a retail‑support task where an agent makes nine well‑formed tool calls but leaves the ticket status as *solved* while the required end state is *hold*.
- The executable check fails because the database disagrees with the claimed outcome.

## ⚙️ Key details
- **Trials:** 121 680 valid trials across 12 LLM models.
- **Failures:** 79 853 attempts failed the executable checks.
- Among failures:
  - 67.24 % terminated cleanly, invoked a state‑changing tool, and reported no final tool error.
  - 77.61 % had wrong field values.
  - 43.30 % produced unintended extra effects.
  - 25.36 % missed required effects.
- **Performance snapshot** (overall pass % where the backend state matched the claim):

| Model | Overall Pass % | Retail Pass % | Auto‑Insurance Pass % |
|-------|----------------|---------------|-----------------------|
| Claude Opus 5.5 | 67.16 | — | — |
| Claude Opus 5 | (two‑thirds of a point below 5.5) | — | — |
| Claude Opus 4.6 | — | 68.62 | 8.30 |
| Kimi‑K3 (open‑weights) | — | (within a point of GPT‑6‑Astra) | — |

- **Observed 20/20**: the literal count of how many of the 507 tasks passed all 20 runs is reported.

## 💡 Why it matters
- Final responses and valid tool calls are only proxies; the **database state is the evidence**.
- A trajectory is a claim, and repetition is the trust test – an agent that succeeds once but fails later is not a reliable refund agent.
- The benchmark highlights that many agents appear correct by tool‑call metrics yet leave incorrect values, unintended side effects, or missing required changes in the backend.
- Domain matters: the same model can score dramatically different percentages on retail versus auto‑insurance tasks.

---
*All statements are drawn directly from the provided evidence.*

![figure](https://cdn-uploads.huggingface.co/production/uploads/64b8491203124195cd795cad/Dzuml_9K2lfRq4hZi17EY.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/64b8491203124195cd795cad/DjaLNZKNeU--Xy2WFCvVX.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/64b8491203124195cd795cad/NONd2WGm4vtGpsVgs-CIq.png)

#ThinkingBox #LLM #AIAgents #Benchmark

---

*Source: [The Agent Said It Was Done. The Database Disagreed.](https://huggingface.co/blog/microsoft/thinkingbox)*
