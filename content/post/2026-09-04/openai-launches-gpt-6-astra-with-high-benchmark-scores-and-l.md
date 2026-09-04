---
title: "OpenAI launches GPT-6 Astra with high benchmark scores and long-context capabilities"
description: "GPT‑6 Astra is rolling out today to a limited set of organizations and, over the coming days, will become available to all ChatGPT Plus, Pro, Business, and Enterprise users, as well as through the..."
date: 2026-09-04T22:05:53+05:30
tags: [OpenAI, GPT6, AIbenchmarks, LongContext, SecurityAI]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI launches GPT-6 Astra with high benchmark scores and long-context capabilities

GPT‑6 Astra is rolling out today to a limited set of organizations and, over the coming days, will become available to all ChatGPT Plus, Pro, Business, and Enterprise users, as well as through the OpenAI API and AWS. The model label for the API will be `gpt-6-astra`.

## 📅 Availability
- Limited‑org rollout begins today.
- General availability will follow for ChatGPT Plus, Pro, Business, Enterprise, API, and AWS users.
- Model identifier on the API: **gpt-6-astra**.

## 💰 Pricing
- API usage priced at the same rate as Claude Fable 5 and 5.1: **$10 per million input tokens** and **$50 per million output tokens**.

## 📊 Performance Benchmarks
| Benchmark | Score | Notes |
|---|---|---|
| ARC‑AGI 3 (released March) | 99.9% | Achieved using OpenAI’s custom **Provider Adapter harness** for $19 K (default harness scored 62.7% for $26 K). |
| ExploitBench | 100% | Compared to GPT‑5.6 Sol’s 78.5%. |
| ExploitGym | 42.4% | Compared to Sol’s 30.3%. |
| SRE‑Bench (binary reverse engineering) | 99.2% within four attempts | Sol achieved 68.7%. |
| OpenAI eight‑needle (long‑context) – 256K–512K tokens | 100% | – |
| OpenAI eight‑needle – 512K–1M tokens | 96.3% | – |

## 🛠️ Technical Highlights
- **Provider Adapter harness** preserves opaque reasoning state between requests and uses compaction for longer conversations, allowing reuse of prior work.
- Demonstrated strong performance on security‑focused benchmarks.
- Shows notable capability on very long context windows (up to 1 million tokens).

## 📈 Strengths vs. Competitors
- Scores higher than Claude Fable on most of OpenAI’s self‑reported benchmarks.
- Leads the **Coding Agent Index** cost‑efficiency frontier: same cost as GPT‑5.6 Sol at max effort but 2 points higher on the index; per task, less than half the cost of Claude Fable 5 for the same score.
- Performs exceptionally on security tasks and long‑context benchmarks.

## ⚖️ Areas Where It Lags
- **Intelligence Index**: scores 61, equal to GPT‑5.6 Sol, 5 points lower than Claude Fable 5.1 (max with fallback), and trails Meta’s Muse Spark 1.3 (max).
- Does not outperform all competitors across every metric.

*I’ll write more about Astra once I get access to it.*

#OpenAI #GPT6 #AIbenchmarks #LongContext #SecurityAI

---

*Source: [GPT‑6 Astra](https://simonwillison.net/2026/Sep/3/gpt6-astra/)*
