---
title: "Moonshot AI Kimi K3 Now Available on Amazon Bedrock"
slug: "moonshot-ai-kimi-k3-now-available-on-amazon-bedrock"
description: "Kimi K3 from Moonshot AI is now available on Amazon Bedrock, providing a new option for knowledge work and coding."
date: 2026-09-19T22:01:30+05:30
tags: [MoonshotAI, AmazonBedrock, KimiK3, AWS, LLM]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21636-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Moonshot AI Kimi K3 Now Available on Amazon Bedrock

Kimi K3 from Moonshot AI is now available on Amazon Bedrock, providing a new option for knowledge work and coding.

## 🔍 Overview
According to Moonshot AI, Kimi K3 is its most capable model and the first open model to reach 2.8 trillion parameters. Key capabilities include:

* Native vision capabilities
* A 1-million-token context window
* Approximate 2.5x improvement in scaling efficiency over Kimi K2

## ⚙️ Key details
Kimi K3 is the first open-weight model on Amazon Bedrock to support explicit prompt caching. This feature allows users to identify reusable prompt prefixes (of at least 1,024 tokens) by adding a `prompt_cache_breakpoint` to supported input content.

* **Caching Process**: Tokens written to cache are billed at a higher rate and kept for at least 30 minutes.
* **Benefits**: Subsequent matching requests are billed at a discounted rate for input tokens and do not count against input-tokens-per-minute quotas, reducing latency and input costs.

## 🚀 Availability
Users can invoke Kimi K3 through a cross-Region inference profile using the following options:

| Profile | Description |
| :--- | :--- |
| `global.moonshotai.kimi-k3` | Routes requests to any supported commercial AWS Region worldwide; costs approximately 10% less than a geographic profile. |
| `us.moonshotai.kimi-k3` | Keeps processing within the US geography for data residency requirements. |

**Prerequisites:**
* An active AWS account with Amazon Bedrock access.
* Python 3.10+.
* AWS IAM permissions: `bedrock:InvokeModel`, `bedrock:InvokeModelWithResponseStream`, and `bedrock:CreateInference`.

## 🧩 How it works
Programmatic access is available via the `bedrock-runtime` endpoint, which supports the Amazon Bedrock Invoke and Converse API APIs, as well as OpenAI-compatible Responses and Chat Completions APIs. Additionally, OpenCode—an open source, model agnostic tool—has a native `amazon-bedrock` model provider that uses the Converse API.

## 💡 Why it matters
Data security is managed within the AWS data boundary. Data is not shared with the model provider and is not used to train the underlying model. Security features include:

* **Zero data retention**: Always enabled for inference requests.
* **Zero operator access**: Prevents AWS operators from accessing prompts and completions during inference.

#MoonshotAI #AmazonBedrock #KimiK3 #AWS #LLM

---

*Source: [Introducing Kimi K3 on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-kimi-k3-on-amazon-bedrock/)*
