---
title: "Guideline-Enhanced GPT‑4.1 Agent Hits 67.5% Pass⁴ on τ²‑bench Retail"
slug: "guideline-enhanced-gpt4-1-agent-hits-67-5-pass4-on-2bench-retail"
description: "A basic retail customer‑service agent built on GPT‑4.1, augmented with automatically extracted behavioral guidelines via the ALTK‑Evolve system, achieved a **67.5 % Pass⁴** score on the τ²‑bench..."
date: 2026-10-20T22:03:21+05:30
tags: [GPT4, CustomerServiceAI, Benchmark, PromptEngineering]
categories: ["AI", "Machine Learning", "AI Agents", "Natural Language Processing", "Evaluation"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6435a1131860001f144239ea/rzXYJh7e7UdoYgCLwOZjH.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# Guideline-Enhanced GPT‑4.1 Agent Hits 67.5% Pass⁴ on τ²‑bench Retail

A basic retail customer‑service agent built on GPT‑4.1, augmented with automatically extracted behavioral guidelines via the ALTK‑Evolve system, achieved a **67.5 % Pass⁴** score on the τ²‑bench benchmark, outperforming every other retail entry in the October 12 2026 leaderboard snapshot.

## 🔍 Overview
- **τ²‑bench** (from Sierra) evaluates how well an LLM‑based agent handles customer‑service conversations under realistic constraints.
- Each task pairs the agent with an LLM‑simulated customer, a set of domain tools (order lookup, refund issuance, flight rebooking), and a written policy document the agent must follow.
- The benchmark includes two domains: **Retail** (40 test tasks) and **Airline** (20 test tasks).
- In the experiment the agent runs on the benchmark’s stock **ReAct** scaffold (a THINK → ACT loop) using **gpt‑4.1** as the agent model and **gpt‑5.5** as the customer‑simulator.

## 🧩 How it works
- **ALTK‑Evolve** builds a playbook of short behavioral rules (e.g., how to authenticate a customer, confirm a transaction, handle a return) by:
  1. Running the baseline ReAct agent on the τ²‑bench training tasks.
  2. Analyzing the agent’s training‑task attempts with the same **gpt‑4.1** model.
  3. Distilling successes and failures into concise guidelines, each tagged with a **support count** (the number of distinct training tasks it appeared in).
- The extracted guidelines are **appended to the system prompt** of the agent for subsequent conversations; no weight updates or human annotation are required.
- Three guideline‑selection configurations are evaluated:
  * **baseline** – no guidelines.
  * **sup3** – keep only guidelines with support ≥ 3 (high‑confidence core).
  * **lossless** – keep every guideline (support ≥ 1).

## 📈 Results
| Domain | Configuration | Mean Accuracy | Pass⁴ | # Guidelines |
|--------|---------------|--------------|------|-------------|
| Retail (40) | baseline | 78.1 % | 57.5 % | 0 |
| Retail (40) | sup3 (support ≥ 3) | 78.8 % (+0.7) | 60.0 % (+2.5) | 31 |
| Retail (40) | lossless (all) | 82.5 % (+4.4) | **67.5 % (+10.0)** | 292 |
| Airline (20) | baseline | 57.5 % | 35.0 % | 0 |
| Airline (20) | sup3 (support ≥ 3) | 60.0 % (+2.5) | 45.0 % (+10.0) | 14 |
| Airline (20) | lossless (all) | 65.0 % (+7.5) | 40.0 % (+5.0) | 101 |

- The **lossless** configuration improves Retail Pass⁴ by **10 percentage points**, reaching the top of the October 12 2026 leaderboard.
- All improvements come **without any model fine‑tuning**; the same **gpt‑4.1** model powers both guideline extraction and the agent itself.

## 💡 Why it matters
- Demonstrates that **automatic rule extraction** from agent trajectories can substantially raise performance on realistic customer‑service benchmarks.
- Shows a path to stronger agents **without expensive weight updates or human‑in‑the‑loop annotation**.
- Highlights the utility of the **ReAct** scaffold combined with a concise, data‑driven prompt playbook.



![figure](https://cdn-uploads.huggingface.co/production/uploads/6435a1131860001f144239ea/HtL2uTn98-xHkcTxKqkFY.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6435a1131860001f144239ea/MsqhICXsHtpJozVFZYEm7.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6435a1131860001f144239ea/iOmv6o938CgNfFlULP-VV.png)

#GPT4 #CustomerServiceAI #Benchmark #PromptEngineering

---

*Source: [ALTK-Evolve: How learned memory tops the τ²-bench leaderboard on customer service tasks without a frontier model](https://huggingface.co/blog/ibm-research/altk-evolve-bc)*
