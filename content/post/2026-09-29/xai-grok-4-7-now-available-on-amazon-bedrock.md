---
title: "xAI Grok 4.7 Now Available on Amazon Bedrock"
slug: "xai-grok-4-7-now-available-on-amazon-bedrock"
description: "xAI’s Grok 4.7 is now available on Amazon Bedrock, introducing a frontier model designed for coding, knowledge work, and long-running agents to the Bedrock model catalog."
date: 2026-09-29T22:02:51+05:30
tags: [xAI, AmazonBedrock, Grok, LLM, CodingAgents]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/28/ML-21934-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# xAI Grok 4.7 Now Available on Amazon Bedrock

xAI’s Grok 4.7 is now available on Amazon Bedrock, introducing a frontier model designed for coding, knowledge work, and long-running agents to the Bedrock model catalog.

## 🔍 Overview

xAI positions Grok 4.7 as its most capable model for knowledge work and coding. The model accepts text and image input and returns text.

## 🧩 How it works

- **Base Model:** Uses a new and larger base model.
- **Training:** Trained with a longer reinforcement learning run over a harder mix of tasks, specifically weighted toward problems requiring many hours to complete.
- **Optimization:** Trained to natively understand the Grok Bot harness to improve general knowledge work and conversational tasks.
- **Reasoning:** Supports configurable reasoning effort at four levels: low, medium, high, and xhigh.
- **Context Window:** Offers a 500K token context window and is designed to make more effective use of this window on long tasks.

## 💡 Why it matters

Improvements have been noted in document and presentation generation, as well as professional knowledge work. Performance gains were measured across several benchmarks:

| Field | Benchmarks |
| :--- | :--- |
| Software Engineering | CursorBench and DeepSWE |
| Terminal and Office Work | Terminal-Bench and AA Briefcase |
| Electrical Engineering | EEBench |
| Legal Work | Harvey Legal Agent Benchmark |
| Clinical Reasoning | HealthBench Professional |

xAI reports the largest gains are in coding agents run in xAI’s own harness and long-horizon agentic knowledge work. These gains are accompanied by roughly double the output tokens per task. Additionally, the model is better at verifying its own work.

## ⚙️ Key details

- **Safeguards:** Built with an entirely new safeguard stack; xAI describes it as the strongest model tested on jailbreak resistance and refusals. 
- **Security:** The model rarely blocks legitimate security work while allowing only a small fraction of risky dual-use prompts. Selected cyber security partners have invite-only access to red-team capabilities for defense research.
- **Intelligence Index:** A composite measurement covering knowledge reliability, reasoning and knowledge, agentic tool use, and long-context work. Grok 4.7 is measured at xhigh reasoning effort for this index.

## 🚀 Availability

- **Endpoint:** Served on the bedrock-runtime endpoint through cross-Region inference profiles (requests use a profile name rather than a bare model ID).
- **Supported APIs:** Supports the Responses, Chat Completions, Converse, and InvokeModel APIs.
- **SDK Integration:** 
    - The OpenAI SDK works via the `/openai/v1` path using a bearer token (either an Amazon Bedrock API key or an AWS IAM short-term token).
    - AWS SDKs access the model through Converse, signing requests with AWS credentials.
- **Optimization:** Implicit prompt caching applies automatically to repeated prompt prefixes.

#xAI #AmazonBedrock #Grok #LLM #CodingAgents

---

*Source: [Grok 4.7 is now available on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/grok-4-7-is-now-available-on-amazon-bedrock/)*
