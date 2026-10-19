---
title: "Bi-directional KV Cache Transfer Cuts Latency for Multi-turn AI Agents"
slug: "bi-directional-kv-cache-transfer-cuts-latency-for-multi-turn-ai-agents"
description: "Multi‑turn agentic workloads accumulate context as an agent reasons, invokes tools, and incorporates earlier results. Each new turn resends the full conversation history – system instructions, prior..."
date: 2026-10-19T22:04:08+05:30
tags: [AIInference, KVCache, MultiTurnAgents, AWS]
categories: ["AI", "Machine Learning", "AI Systems", "Cloud Computing", "Inference Optimization"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21811-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Bi-directional KV Cache Transfer Cuts Latency for Multi-turn AI Agents

Multi‑turn agentic workloads accumulate context as an agent reasons, invokes tools, and incorporates earlier results. Each new turn resends the full conversation history – system instructions, prior prompts, tool results, and model responses – causing the growing context to be processed repeatedly.

## 🔍 Overview
- In Prefill‑decode (P‑D) disaggregation, a **prefill node** builds the key‑value (KV) cache for the prompt, while a **decode node** retrieves those KV blocks to generate the response.
- Conventional disaggregated serving moves KV cache only from prefill → decode. This one‑directional flow creates two inefficiencies for multi‑turn workloads:
  1. After a response, the decode node holds KV entries for both the prompt and newly generated tokens. The prefill node cannot retrieve these entries for the next turn and must recompute KV projections for the previous response tokens.
  2. Session state is kept on the decode node but not on prefill nodes, increasing the chance of cache eviction for active sessions on the prefill side.
- When a full cache miss occurs, the prefill node recomputes KV projections for the entire conversation history, consuming more accelerator capacity and increasing time‑to‑first‑token (TTFT).

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21811-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21811-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21811-3.png)

#AIInference #KVCache #MultiTurnAgents #AWS

---

*Source: [Improve TTFT for multi-turn agentic workloads with bi-directional KV transfer in vLLM | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/improve-ttft-for-multi-turn-agentic-workloads-with-bi-directional-kv-transfer-in-vllm/)*
