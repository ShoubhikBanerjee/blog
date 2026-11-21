---
title: "LLM Benchmark Update: DeepSeek V4 Pro and OpenCode Harness Limitations"
slug: "llm-benchmark-update-deepseek-v4-pro-and-opencode-harness-limitations"
description: "This update documents new developments in an autonomous coding benchmark repository, specifically addressing how OpenCode harness effects impact cross-model comparisons and the recent successful..."
date: 2026-11-21T06:15:51+05:30
tags: [LLMBenchmarks, DeepSeek, OpenCode, Claude, AIEngineering]
categories: ["AI", "Large Language Models", "AI Benchmarking", "Software Development", "Agent Architecture"]
image: "https://avatars.githubusercontent.com/u/2840?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LLM Benchmark Update: DeepSeek V4 Pro and OpenCode Harness Limitations

This update documents new developments in an autonomous coding benchmark repository, specifically addressing how OpenCode harness effects impact cross-model comparisons and the recent successful benchmarking of DeepSeek V4 Pro.

## 🔍 Overview
- **DeepSeek V4 Pro Benchmark**: A new round (dated 2026-05-04) successfully measured DeepSeek V4 Pro using the `deepclaude` env-swap shim via Claude Code's autonomous loop. This resolved a prior inability to measure the model caused by an `opencode` reasoning_content interop bug.
- **Harness Limitations**: It was identified that `opencode` substring-matches model IDs to inject family-specific system prompts (e.g., bespoke prompts for Claude, GPT, Gemini, Kimi) versus a generic default for others (DeepSeek, Qwen, GLM). Consequently, cross-family score differences may reflect prompt tuning rather than model capability.
- **Multi-Agent Strategy**: An analysis (dated 2026-04-25) evaluated whether pairing a planner with a cheaper executor is cost-effective compared to using a solo Opus model.

## ⚙️ Key Details
The benchmark uses a fixed Rails application brief to compare local and cloud models. The current successful execution path involves a two-phase OpenRouter run:
- **Phase 1**: Builds the Rails app.
- **Phase 2**: Continues the same session to validate local boot, docker build, and docker compose up --build.

**Current Model Rankings (0-100 Rubric)**
| Model | Score | Notes |
| :--- | :--- | :--- |
| Claude Opus 4.7 | 97 | Benchmark leader; ~$1.10/run |
| GPT 5.4 xHigh | 97 | Ties Opus; ~$16/run (15x cost) |
| GPT 5.5 xHigh | 96 | 40% cheaper and 20% faster than 5.4 (~$10/run) |
| Claude Opus 4.8 | 95 | Newest Opus run; 34 tests, 16m48s |
| Kimi K2.6 | 87 | Best value; ~$0.30/run |
| Claude Opus 4.6 | 83 | Missing rescue around LLM calls |
| Gemini 3.1 Pro | 82 | Real Turbo Streams, cache-backed persistence |

**Evaluation Methodology**
- **Rubric**: Rankings are based on 8 dimensions including deliverables, RubyLLM correctness, tests, error handling, persistence, Hotwire, architecture, and production-readiness.
- **Metric Warning**: File count and test count are considered misleading. For example, Kimi K2.5 wrote 37 tests but none mocked RubyLLM, while Gemini 3.1 Pro scored higher with only 11 tests due to correct signatures.
- **Hallucination Penalty**: A "benchmark-killing pattern" occurs when models hallucinate APIs and then write tests that mock those hallucinations (e.g., DeepSeek V3.2 mocking a non-existent `RubyLLM::Client.any_instance`).

#LLMBenchmarks #DeepSeek #OpenCode #Claude #AIEngineering

---

*Source: [akitaonrails/llm-coding-benchmark](https://github.com/akitaonrails/llm-coding-benchmark)*
