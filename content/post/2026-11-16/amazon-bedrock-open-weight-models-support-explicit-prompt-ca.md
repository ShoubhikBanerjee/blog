---
title: "Amazon Bedrock Open-Weight Models Support Explicit Prompt Caching"
slug: "amazon-bedrock-open-weight-models-support-explicit-prompt-caching"
description: "Open-weight models on Amazon Bedrock now support explicit prompt caching. This update allows developers to reuse computed prompt prefixes across requests, reducing input costs and response latency by..."
date: 2026-11-16T22:14:27+05:30
tags: [AmazonBedrock, PromptCaching, AWS, OpenWeightModels, LLM]
categories: ["AI", "Machine Learning", "Cloud Computing", "Large Language Models", "Developer Tools"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22160-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Open-Weight Models Support Explicit Prompt Caching

Open-weight models on Amazon Bedrock now support explicit prompt caching. This update allows developers to reuse computed prompt prefixes across requests, reducing input costs and response latency by reading repeated context from cache instead of processing it again.

## 🔍 Overview

Prompt caching reuses the computed state of a matching prompt prefix. When a request starts with the same content as an earlier one, Amazon Bedrock reads that prefix from the cache and processes only the remainder. Cache reads are billed at a lower rate than standard input, meaning savings grow each time a prefix is reused. Depending on the model, cache writes can be billed at a higher rate than standard input, but Amazon Bedrock manages the cache automatically.

## 🧩 How it works

Developers can use implicit caching, which works automatically on a best-effort basis, or explicit caching, where specific reusable prefixes are marked. 

*   **Implicit Caching:** Amazon Bedrock reuses eligible prefixes automatically. In a conversation, each request resends the full context, so the previous request becomes the cached prefix for the next one. As recommended by the prompt caching guide, static content should be placed first and dynamic content last to keep the start of the prompt stable. If an early part changes, the cache is rebuilt from that point.
*   **Explicit Caching:** Users mark the end of each reusable prefix with a cache breakpoint. Content up to each breakpoint is written to cache once and read on later requests, while content after the last breakpoint is processed on every request. Users can add several breakpoints, up to the model's maximum, to cache layers that change at different rates. This method limits cache writes to the shared prefix, preventing higher write-rate billing for content that is never read back on models that charge for cache writes.

On the Chat Completions API, explicit caching is configured using `prompt_cache_options` with the mode set to `explicit`, plus one or more `prompt_cache_breakpoint` markers.

## ⚙️ Key details

| Feature | Detail |
| :--- | :--- |
| **Caching Modes** | Implicit (automatic) and Explicit (user-marked) |
| **Data Privacy** | Prompts and outputs are not shared with the model provider or used to train models |
| **Configuration** | Use `prompt_cache_breakpoint` markers on the Chat Completions API |
| **TTL** | Time to live resets with each cache hit; specific durations vary by model |
| **Minimums** | Minimum token count and maximum breakpoints vary by model; check the model card |

Amazon Bedrock checks the prompt cache for a matching prefix, reads a matching prefix from cache, and writes new cacheable content to cache. 

## 🚀 Availability

Amazon Bedrock manages the cache for you. Model availability and prompt caching support vary by AWS Region. An AWS account with access to the selected model on Amazon Bedrock is required. Developers should check the model card for the Regions that the model supports, as well as specific caching modes, minimum prefix lengths, and entry retention times.

Requests are sent to the Amazon Bedrock Runtime endpoint in your selected Region, authenticated with a short-term Amazon Bedrock API key.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22160-3.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22160-4.png)

#AmazonBedrock #PromptCaching #AWS #OpenWeightModels #LLM

---

*Source: [Use prompt caching with open-weight models on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/use-prompt-caching-with-open-weight-models-on-amazon-bedrock/)*
