---
title: "Kimi K3.1 Pro Highspeed Now Available on Amazon Bedrock"
slug: "kimi-k3-1-pro-highspeed-now-available-on-amazon-bedrock"
description: "Kimi K3.1 Pro Highspeed from Moonshot AI is now available on Amazon Bedrock. Part of Moonshot AI’s new K3.1 series, it is a post-trained version of Kimi K3 with the same 3T-class open-weight..."
date: 2026-11-11T18:02:06+05:30
tags: [A, m, a, z, o, n, B, e, d, r, o, c, k, K, i, m, i, K, 3, A, I, M, o, d, e, l, O, p, e, n, A, I, C, o, m, p, a, t, i, b, l, e]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "A", "I", "A", "g", "e", "n", "t", "s", ",", "C", "l", "o", "u", "d", "C", "o", "m", "p", "u", "t", "i", "n", "g", ",", "S", "o", "f", "t", "w", "a", "r", "e", "D", "e", "v", "e", "l", "o", "p", "m", "e", "n", "t"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22229-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Kimi K3.1 Pro Highspeed Now Available on Amazon Bedrock

Kimi K3.1 Pro Highspeed from Moonshot AI is now available on Amazon Bedrock. Part of Moonshot AI’s new K3.1 series, it is a post-trained version of Kimi K3 with the same 3T-class open-weight architecture and 1-million-token context window.

## 🔍 Overview
The model is trained with substantially more post-training compute. According to Moonshot AI, this extra training targets long-horizon agentic work and fewer factual errors. It improves professional tasks such as financial modeling and office documents, and coding for game engines, 3D scenes, and computer-aided design (CAD) scripts.

## 🚀 Performance & Capabilities
Kimi K3.1 Pro Highspeed generates output tokens at a higher rate. Moonshot AI reports 2–3 times the speed of Kimi K3.1 Pro. The model supports tool calling, structured output, configurable reasoning, image input, and streaming.

## 🧠 Reasoning
Kimi K3.1 Pro Highspeed always reasons before it answers. You can control the reasoning effort with the `reasoning_effort` parameter: low, high, or max. If you do not set it, the model uses max. A lower value is the most direct way to reduce latency and output tokens on simpler tasks.

## 💰 Pricing & Tiers
The model is available in Standard, Priority, and Flex tiers. The Flex tier serves Kimi K3.1 Pro Highspeed at half the Standard price, in exchange for potentially longer response times. It is well suited to workloads where cost efficiency is a higher priority than response time, such as model evaluations, content summarization, and background tasks in agentic workflows. Because you choose the tier for each request, one application can mix tiers. Your on-demand quota is shared across the Standard, Priority, and Flex tiers.

## 🔒 Security
You can adopt Kimi K3.1 Pro Highspeed without changing your security posture. Your data is processed within the AWS data boundary, isn’t shared with Moonshot AI, and isn’t used to train the model. Zero data retention is always enabled for inference requests, and with zero operator access, AWS operators can’t view your prompts and completions during inference.

## 🛠️ Integration
From code, Kimi K3.1 Pro Highspeed is available on the bedrock-runtime endpoint through the OpenAI-compatible Chat Completions and Responses APIs, and through the Amazon Bedrock Converse and Invoke APIs. We recommend the Chat Completions API. If you already build with Kimi K3, you can try it by changing the model ID in your existing code.

### Regional Profiles
- `global.moonshotai.kimi-k3.1`: Routes requests to any supported commercial AWS Region, and costs less per token than the geographic profiles.
- `us.moonshotai.kimi-k3.1`: Keeps processing within US Regions.
- `in.moonshotai.kimi-k3.1`: Keeps processing within India Regions.

## 💾 Caching
Agents and coding assistants resend the same large prefix on every turn: system instructions, tool definitions, repository conventions, and reference documents. Kimi K3.1 Pro Highspeed caches repeated prefixes automatically, and with explicit prompt caching, you can mark where the stable prefix ends to improve your cache hit rate. Later requests reuse that prefix instead of processing it again, which lowers both latency and input cost for long, repeated context. Explicit caching works on the Chat Completions, Responses, and Invoke APIs, but not on Converse.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/11/ml-22229-opencode-connect-dialog.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/11/ml-22229-opencode-select-variant.png)

#A #m #a #z #o #n #B #e #d #r #o #c #k #, # #K #i #m #i #K #3 #, # #A #I #M #o #d #e #l #, # #O #p #e #n #A #I #C #o #m #p #a #t #i #b #l #e

---

*Source: [Introducing Kimi K3.1 Pro on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-kimi-k3-1-pro-on-amazon-bedrock/)*
