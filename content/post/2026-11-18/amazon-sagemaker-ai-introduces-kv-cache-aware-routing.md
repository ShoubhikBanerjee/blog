---
title: "Amazon SageMaker AI introduces KV cache-aware routing"
slug: "amazon-sagemaker-ai-introduces-kv-cache-aware-routing"
description: "Today, Amazon SageMaker AI introduces KV cache-aware routing (KV-aware routing), a new routing strategy for real-time endpoints. It uses the cache state that the model container reports to send each..."
date: 2026-11-18T18:09:03+05:30
tags: [AmazonSageMaker, LLM, KVCache, Routing, Inference]
categories: ["AI", "Machine Learning", "Cloud Computing", "Large Language Models", "Inference Optimization"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22381-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker AI introduces KV cache-aware routing

Today, Amazon SageMaker AI introduces KV cache-aware routing (KV-aware routing), a new routing strategy for real-time endpoints. It uses the cache state that the model container reports to send each request to an instance that already holds a long cached match for its prompt and isn’t too busy.

## 🔍 Overview

KV-aware routing is designed for teams that serve large language models (LLMs) with multi-turn conversations, long shared prompts, or heavy load. It addresses limitations in the previously introduced prefix-aware routing, which infers where a prefix is cached from the request alone. Because prefix-aware routing hashes the start of the request, it cannot tell when an instance has evicted that cache. Consequently, if an instance evicts older KV cache entries when its GPU memory fills up, the router keeps sending matching requests there as if the cache were still warm. Additionally, in multi-turn chats, each turn adds to the history; while a request is shorter than the configured `PrefixLength`, every new turn changes the text the router hashes, so the next turn can land on a different instance than the one that cached the earlier turns.

## 🧩 How it works

A model keeps the work it did on a prompt in GPU memory, the KV cache, and skips that work when the same start reaches the same instance again. KV-aware routing operates through three main components:

*   **Model Container Reporting**: The model container reports what it has cached.
*   **Managed Cache Index**: SageMaker AI keeps a managed cache index of that state for the endpoint.
*   **Endpoint Routing**: The endpoint uses the index to choose an instance for each request.

When a request arrives, the endpoint tokenizes the prompt and looks up the tokens in the index. The index holds only pointers: one-way, truncated hashes of cached content, each mapped to the instance or inference component copy that holds it. It never stores prompts, token IDs, request payloads, or KV tensors. Because the index matches on tokens rather than a fixed number of bytes, a multi-turn history can match in full as it grows. If instance A holds the cached start of a conversation, the next turn of that conversation goes to A.

The endpoint picks among candidates by weighing how much of the prompt each one has cached against how busy it is. A candidate that is too busy is skipped, so if the instance with the longest match is busy, the request goes to the next-best one that is available. If no candidate has a useful match or all of them are busy, the request falls back to load-aware routing.

## ⚙️ Key details

You turn on KV-aware routing in two places:

*   Add one environment variable to your model so the container reports its cache contents.
*   Set `RoutingStrategy` to `KV_AWARE` in the endpoint configuration.

Specifically, when you turn events on with `SM_VLLM_KV_EVENTS_CONFIG`, the container publishes a KV cache event each time it stores or evicts cache entries, and SageMaker AI uses these events to keep the index current. Clients call the endpoint with the same APIs as before. You do not configure a concurrency threshold for this, as you do with prefix-aware routing.

## 💡 Why it matters

This strategy ensures that requests sharing a prompt are routed to instances where that prompt is already in the GPU memory cache, maximizing computational efficiency. By tracking actual cache eviction and storage events rather than relying on static prefix hashes, the system prevents routing requests to instances where the cache has been cleared due to memory pressure.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22381-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22381-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22381-3-1.png)

#AmazonSageMaker #LLM #KVCache #Routing #Inference

---

*Source: [Amazon SageMaker AI real-time endpoints now support KV cache aware routing | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/amazon-sagemaker-ai-real-time-endpoints-now-support-kv-cache-aware-routing/)*
