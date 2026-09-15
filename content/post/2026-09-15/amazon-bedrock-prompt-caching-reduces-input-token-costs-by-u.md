---
title: "Amazon Bedrock prompt caching reduces input token costs by up to 90 percent"
slug: "amazon-bedrock-prompt-caching-reduces-input-token-costs-by-up-to-90-percent"
description: "Amazon Bedrock now supports prompt caching, which allows users to store snapshots of partially processed input to reduce costs and time-to-first-token (TTFT) when repeatedly sending the same context..."
date: 2026-09-15T22:08:30+05:30
tags: [AmazonBedrock, AWS, PromptCaching, MachineLearning, GenerativeAI]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-20790-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock prompt caching reduces input token costs by up to 90 percent

Amazon Bedrock now supports prompt caching, which allows users to store snapshots of partially processed input to reduce costs and time-to-first-token (TTFT) when repeatedly sending the same context to foundation models.

## 🔍 Overview

Prompt caching stores a snapshot of partially processed input so that subsequent requests with the same prefix skip redundant computation. This feature is applicable to parts of conversation context such as system prompts, documents, and tool definitions.

* **Cost Savings:** For workloads with repeated context, savings can reach approximately 75 percent on input token costs.
* **Performance:** Cache hits can reduce time-to-first-token (TTFT) and lower costs for cached input tokens by up to 90 percent.
* **Consistency:** Caching occurs without changing the model or prompt quality.

## 🧩 How it works

Users include a `cachePoint` marker in their request to indicate where a checkpoint should be placed. Amazon Bedrock evaluates whether the content preceding that marker matches an existing cache entry.

* **Cache Hit:** If a match exists, the model skips reprocessing those tokens and begins generation from the cached state.
* **Cache Miss:** If no match exists, the model processes the full content and writes the result to the cache for potential future requests.
* **Syntax:** The Converse API `cachePoint` syntax is identical across supported model families, including Anthropic Claude and Amazon Nova. To implement this, a `cachePoint` content block is placed after static content and before the dynamic question.

## ⚙️ Key details

Cache entries are scoped to individual AWS accounts and AWS Regions. Each cache checkpoint must meet a minimum token threshold to activate.

| Model Family | Minimum Token Threshold |
| :--- | :--- |
| Anthropic Claude Sonnet 4.5 and 4.6 | 1,024 tokens |
| Anthropic Claude Opus models | 4,096 tokens |

**Expiration (TTL):**
* **Default:** 5 minutes.
* **Select models:** Up to 1 hour.

**Pricing Structure:**

| Token Type | Cost relative to standard input |
| :--- | :--- |
| `cacheWriteInputTokens` | 25% higher |
| `cacheWriteInputTokens` (1-hour TTL) | 100% higher (2x) |
| `cacheReadInputTokens` | 90% lower |

**Implementation Requirements:**
* An AWS account with Amazon Bedrock access in a supported AWS Region (such as us-west-2).
* Python 3.10 or later.

#AmazonBedrock #AWS #PromptCaching #MachineLearning #GenerativeAI

---

*Source: [Optimizing cost and latency with Amazon Bedrock prompt caching | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/optimizing-cost-and-latency-with-amazon-bedrock-prompt-caching/)*
