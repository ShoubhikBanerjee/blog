---
title: "Researchers Release Realtime-Bench to Evaluate AI Agent Performance in Dynamic Environments"
slug: "researchers-release-realtime-bench-to-evaluate-ai-agent-performance-in-dynamic-environments"
description: "Researchers from the University of Texas at Austin, Ohio State University, University of Illinois at Urbana-Champaign, NVIDIA, Northwestern University, and Steadyworks have introduced Realtime-Bench...."
date: 2026-11-02T22:02:19+05:30
tags: [RealtimeBench, AIagents, MachineLearning, OpenAI, NVIDIA]
categories: ["AI", "AI Agents", "Machine Learning", "Benchmark Testing"]
image: "https://substackcdn.com/image/fetch/$s_!3yYS!,w_1200,h_675,c_fill,f_jpg,q_auto:good,fl_progressive:steep,g_auto/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd6d17996-2bef-40a4-abe3-be72a0e8a227_258x258.png"
author: "Shoubhik Banerjee"
draft: false
---

# Researchers Release Realtime-Bench to Evaluate AI Agent Performance in Dynamic Environments

Researchers from the University of Texas at Austin, Ohio State University, University of Illinois at Urbana-Champaign, NVIDIA, Northwestern University, and Steadyworks have introduced Realtime-Bench. This new benchmark is a suite of curated dynamic tasks designed to measure how delayed actions directly affect the success of AI agents.

## 🔍 Overview
Realtime-Bench consists of 50 interactive game and web tasks. The tasks are split across two primary domains:

*   **30 Web Tasks:** Spanning four categories including travel, e-commerce, service, and security.
*   **20 Game Tasks:** Covering arcade, puzzle, strategy, and simulation genres.

## 🧩 How it works
The test is designed to probe for three specific qualities in AI models:

| Quality | Description |
| :--- | :--- |
| RT-Perceive | Temporal state awareness where models use observations to track changes in the world. |
| RT-Deliberate | Adaptive deliberation where models alter reasoning length and depth based on available time. |
| RT-Act | Time-aware action selection where models must appropriately time their actions for the situation. |

For example, an agent purchasing a ticket must track sale status (RT-Perceive), limit deliberation when the purchase window is closing (RT-Deliberate), and choose between waiting for sales to open or purchasing while tickets remain available (RT-Act).

## ⚙️ Key details
The benchmark evaluates models under three different clock conditions to understand performance nuances:

*   **Wall clock:** Tests performance under real-world latency.
*   **Paused clock:** Allows the environment to be paused to establish a baseline capability.
*   **Token clock:** Advances the environment at a fixed rate per generation token, meaning more tokens delay execution regardless of actual inference latency.

Researchers tested a wide range of frontier models including OpenAI's GPT-6-Astra and GPT-Realtime-2, Anthropic's Claude Fable 5.1, and Google's Gemini 3.8 Live. Chinese models from Deepseek (V4.1) and Moonshot AI (Kimi-K3) were also included in the evaluation.

## 💡 Why it matters
Realtime-Bench serves as an effective proxy for identifying where AI agents are likely to break. Current results indicate that AI agents cannot yet be expected to perform well on these tasks. GPT-6 Astra (high) achieved the highest pass rate on the 'wall clock' setting with only 36%. In contrast, high-reasoning models achieved 70% to 80% success when the clock was paused, highlighting the significant impact of real-time constraints on model performance.

![figure](https://substackcdn.com/image/fetch/$s_!X6SM!,e_trim:10:white/e_trim:10:transparent/h_72,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9b933b21-aef3-4abf-8aa2-c6b2b6dcd17e_1316x448.png)

#RealtimeBench #AIagents #MachineLearning #OpenAI #NVIDIA

---

*Source: [Import AI 479: Spacewar; low-latency tasks versus LLMs; Genie 4](https://importai.substack.com/p/import-ai-479-spacewar-low-latency)*
