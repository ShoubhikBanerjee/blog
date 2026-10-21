---
title: "OpenAI GPT-5.6, GPT-6, and GPT-6.1 models now available on Amazon Bedrock in Canada"
slug: "openai-gpt-5-6-gpt-6-and-gpt-6-1-models-now-available-on-amazon-bedrock-in-canada"
description: "OpenAI’s latest GPT‑5.6, GPT‑6, and GPT‑6.1 model families have been added to Amazon Bedrock, and developers can now invoke them from the Canada (Central) and Canada West (Calgary) AWS regions."
date: 2026-10-21T06:09:12+05:30
tags: [OpenAI, AmazonBedrock, AIModels]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21126-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI GPT-5.6, GPT-6, and GPT-6.1 models now available on Amazon Bedrock in Canada

OpenAI’s latest GPT‑5.6, GPT‑6, and GPT‑6.1 model families have been added to Amazon Bedrock, and developers can now invoke them from the Canada (Central) and Canada West (Calgary) AWS regions.

## 🔍 Overview
- New OpenAI model variants (GPT‑5.6, GPT‑6, GPT‑6.1) are accessible via Amazon Bedrock.
- The models accept text and image inputs, return text, and support a 1‑million‑token context window, reasoning mode, and tool calling.
- Prompt caching is supported for all three model families.

## 🧩 How it works
- Your application calls the Amazon Bedrock Runtime endpoint in your source Region (ca‑central‑1 or ca‑west‑1).
- Amazon Bedrock routes the request to a supported destination Region for processing (cross‑Region inference, CRIS).
- Inference is processed in North America, with data‑residency controls as described in the post.
- US geographic profiles route requests to your Canadian source Region and US Regions; the global profile routes to any commercial AWS Region where the model is deployed.

## ⚙️ Key details
### Model variants and primary use cases
| Model | Primary focus |
|-------|----------------|
| GPT‑5.6 Sol | High reasoning, coding, and agentic workloads |
| GPT‑5.6 Terra | Balanced performance and cost for everyday production |
| GPT‑5.6 Luna | Fast and affordable for high‑volume, latency‑sensitive applications |
| GPT‑6 Astra | Complex end‑to‑end reasoning and agentic tasks |
| GPT‑6 Sol | Strong reasoning and coding for recurring tasks with economics suited to regular use |
| GPT‑6 Luna | Fast, low‑cost inference for high‑volume repeated tasks with adjustable reasoning effort per request |
| GPT‑6.1 Sol | Strong reasoning and coding for tasks where both performance and cost matter |

### Common capabilities
- Text and image inputs; output is text.
- 1‑million‑token context window.
- Reasoning mode and tool calling.
- Prompt caching (see Prompt caching section).
- Available through OpenAI Responses API, OpenAI Chat Completions API, and Amazon Bedrock Converse API (bedrock‑runtime endpoint).

## 🚀 Availability
- **Regions:** Canada (Central) `ca-central-1` and Canada West (Calgary) `ca-west-1`.
- The global profile for GPT‑5.6 is only in `ca-central-1`; from `ca-west-1` use the US geographic profile for GPT‑5.6.
- Access requires an AWS account with the appropriate Canadian region enabled.
- Development environment: Python 3.9+ with `openai`, `boto3`, and `aws-bedrock-token-generator` packages.
- Quick start: attach the managed policy `AmazonBedrockLimitedAccess`.
- Additional permissions: if authenticating via API‑key (bearer token), grant `bedrock:CallWithBearerToken`; for the Responses API, add `bedrock:InvokeModel` on `arn:aws:bedrock:ca-central-1:*:project/default`.

## 💡 Why it matters
- Enables Canadian developers to keep inference workloads within North America, satisfying data‑residency requirements.
- Offers a range of model sizes and cost/performance trade‑offs to match diverse workloads, from high‑throughput low‑cost inference to complex agentic reasoning.
- Prompt caching reduces latency and cost for recurring prompts.
- Unified access via Bedrock APIs simplifies integration with existing AWS‑based applications.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21126-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21126-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21126-3.jpg)

#OpenAI #AmazonBedrock #AIModels

---

*Source: [Access OpenAI GPT models on Amazon Bedrock from Canada with cross-Region inference | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/access-openai-gpt-models-on-amazon-bedrock-from-canada-with-cross-region-inference/)*
