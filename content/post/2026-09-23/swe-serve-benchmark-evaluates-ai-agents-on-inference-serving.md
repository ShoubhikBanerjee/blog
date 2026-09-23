---
title: "SWE-Serve Benchmark Evaluates AI Agents on Inference-Serving Stack Changes"
slug: "swe-serve-benchmark-evaluates-ai-agents-on-inference-serving-stack-changes"
description: "Researchers have introduced SWE-Serve, a benchmark designed to evaluate the ability of AI agents to handle repository-scale changes across the inference-serving stack."
date: 2026-09-23T22:05:40+05:30
tags: [SWEServe, SGLang, AIagents, InferenceServing, LLM]
categories: ["AI", "Machine Learning", "AI Agents", "Software Engineering"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image1-16-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# SWE-Serve Benchmark Evaluates AI Agents on Inference-Serving Stack Changes

Researchers have introduced SWE-Serve, a benchmark designed to evaluate the ability of AI agents to handle repository-scale changes across the inference-serving stack.

## 🔍 Overview
SWE-Serve evaluates gaps in AI agent performance by testing changes to SGLang, an open-source system for serving large language models. The benchmark turns 83 merged SGLang pull requests into 53 executable tasks across six inference-engineering families, including:
* Model enablement
* Decoding
* Caching
* Scheduling
* Serving APIs
* Runtime performance

## ⚙️ Key Details
Tasks in the benchmark are distributed by hardware and scope:
* **Hardware:** 12 tasks run on CPU and 41 use a single NVIDIA H100.
* **Task Composition:** 37 tasks originate from a single upstream pull request, while 16 combine two to six related changes.
* **Complexity:** The median reference solution involves modifying 553 lines across seven files.
* **Verification:** A typical verifier includes seven tests for new behavior and 10 regression tests. A patch passes if it satisfies a hidden verifier on the declared hardware.

## 🧩 How it works
SWE-Serve includes 19 tasks that utilize a live serving interface to test patches. These 19 tasks contain 276 live serving tests, 242 of which are sourced or adapted from SGLang. Additionally, three tasks enforce a calibrated performance gate on an H100.

One specific task requires an agent to add serving support for Qwen3.5 models; the agent must ensure both the 0.8B dense model and the 35B-A3B MoE model load and serve through normal SGLang interfaces on one H100.

## 💡 Why it matters
Evaluation using mini-swe-agent—a minimal software-engineering agent using only Bash under closed-book conditions—revealed a performance gap when live-serving checks are applied:

* **Live Serving Impact:** Across 19 tasks, patches passed 69.4% of the time when live-serving checks were excluded, but only 45.9% with the complete verifier. 
* **Failure Rate:** Approximately one in three patches that passed other checks failed live-serving tests. Specifically, 16 of 33 patches passed every other check but failed at least one live serving test.
* **Domain Complexity:** Tasks confined to one runtime domain had a 69.0% pass rate, whereas tasks spanning more than one runtime domain had a 47.7% pass rate.

Across 11 models and 31 model-effort configurations, mean pass@1 ranged from 34.6% to 75.5%. Agent sessions were capped at 350 steps and 210 minutes.

#SWE-Serve #SGLang #AIagents #InferenceServing #LLM

---

*Source: [How SWE-Serve Exposes the Gap Between Local Tests and Live Serving | NVIDIA Technical Blog](https://developer.nvidia.com/blog/how-swe-serve-exposes-the-gap-between-local-tests-and-live-serving/)*
