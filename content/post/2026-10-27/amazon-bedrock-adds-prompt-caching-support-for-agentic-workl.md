---
title: "Amazon Bedrock adds prompt‑caching support for agentic workloads"
slug: "amazon-bedrock-adds-promptcaching-support-for-agentic-workloads"
description: "Amazon Bedrock now supports prompt caching that reduces the repeated work of sending large, unchanging prompt prefixes for each model call."
date: 2026-10-27T22:02:24+05:30
tags: [AmazonBedrock, PromptCaching, AIAgents]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-22246-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock adds prompt‑caching support for agentic workloads

Amazon Bedrock now supports prompt caching that reduces the repeated work of sending large, unchanging prompt prefixes for each model call.

## 🔍 Overview
When an agent takes a step—calling a tool, reading the result, then deciding the next action—it must resend the entire story (tool definitions, instructions, previous calls, and results) because the model has no internal memory between requests. Prompt caching lets the service store that reusable prefix and reuse it on later requests, cutting the input cost.

## 🧩 How it works
- The model predicts the next token **only** from the input you provide; there is no hidden state kept between calls.
- On the first request, the service performs a *prefill*: it reads every input token and builds key‑value (KV) vectors, which become the model’s working state.
- Prompt caching saves this KV state, which includes the system prompt, tools, content, history, and so on.
- For a later request that starts with the **exact same text**, the caching service loads the saved state instead of recomputing it, then processes only the new payload.

## ⚙️ Modes and configuration
- **Implicit caching** – Bedrock automatically selects where the reusable prefix ends as the conversation grows.
- **Explicit caching** – Your code marks the cache boundary with `prompt_cache_breakpoint` and can reuse shared content such as tools and instructions across sessions or helper agents.
- The reusable prefix must be at least **1,024 tokens** to qualify.
- `prompt_cache_key` tells the service which requests should share a cache.
- Setting `store=False` leaves conversation history in your application instead of the service.

## 📊 Observed performance
In a test using explicit caching, a roughly **4,000‑token** tools‑and‑instructions prefix wrote **4,120 tokens** on the first request and read those **4,120 tokens** on later requests. The user task that follows the cache boundary does not trigger a write to the cache.

## 💡 Best practices
- Prompt caching works **only** when you pass exactly the same text.
- Serialize the agent’s instructions and tool lists **identically** each time.
- Place any variable data (date, user name, request ID, etc.) **after** the cached instructions.
- When content varies frequently (different tools or evolving conversation), prefer **implicit mode** to let the service manage the cache boundary.
- Keep the reusable prefix long enough (≥1,024 tokens) to meet the caching requirement.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-22246-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-22246-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-22246-3-1.png)

#AmazonBedrock #PromptCaching #AIAgents

---

*Source: [Groundhog Day for AI agents: Prompt caching patterns for using OpenAI models on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/groundhog-day-for-ai-agents-prompt-caching-patterns-for-using-openai-models-on-amazon-bedrock/)*
