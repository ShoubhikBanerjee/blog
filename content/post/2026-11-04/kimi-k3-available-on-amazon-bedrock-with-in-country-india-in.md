---
title: "Kimi K3 Available on Amazon Bedrock with In‑Country India Inference and Cost‑Saving Features"
slug: "kimi-k3-available-on-amazon-bedrock-with-incountry-india-inference-and-costsaving-features"
description: "Moonshot AI’s Kimi K3 foundation model is now accessible through Amazon Bedrock with in‑country inference in India and new cost‑saving prompt‑caching."
date: 2026-11-04T06:03:46+05:30
tags: [KimiK3, AmazonBedrock, AIInference, MultiModal]
categories: ["AI", "Machine Learning", "Generative AI", "Cloud Computing", "Computer Vision"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22220-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Kimi K3 Available on Amazon Bedrock with In‑Country India Inference and Cost‑Saving Features

Moonshot AI’s Kimi K3 foundation model is now accessible through Amazon Bedrock with in‑country inference in India and new cost‑saving prompt‑caching.

## 🔍 Overview
- Kimi K3 is a **multi‑modal, open‑weight foundation model** that provider Moonshot AI reported achieved frontier‑level coding and general agentic intelligence at release.  
- Amazon Bedrock now supports **in‑country inference in India** for Kimi K3, unblocking local workloads with strict data residency requirements.

## ⚙️ How it works
- **Cross‑Region inference**: You invoke the model from any AWS source Region. Amazon Bedrock processes the request in one of multiple destination Regions.  
- Data is **encrypted in transit** and stays on the AWS network, never traversing the public internet or requiring a multi‑Region VPC.  
- The **inference profile ID** you specify controls which destination Regions are eligible.  
- The **Global profile** `global.moonshotai.kimi‑k3` is recommended for most use cases (lowest cost, most broadly available).  
- An **India‑only profile** `in.moonshotai.kimi‑k3` ensures processing stays within Mumbai and Hyderabad Regions.

### API surface
| API | Description |
|-----|-------------|
| Chat Completions | OpenAI‑compatible messages input and assistant‑message output |
| Responses | OpenAI‑compatible input and structured output items |
| Converse | Standardized messages, content blocks, and inference parameters across supported models |
| InvokeModel | Model‑specific JSON request and response bodies |

## 🚀 Key details
- **Prompt caching** cuts LLM costs by **80 %** and makes multi‑turn chats **85 % faster**.  
- Supports **images, PDFs, and a range of other file types**; input files can be sent by base‑64 encoding.  
- Directly reads and reasons about images, including multilingual text, removing the need for separate OCR or translation services.  
- For OCR‑critical use cases, set the **image detail parameter to high**.  
- Streaming, tool calling, and structured outputs are available across both the Chat Completions and Responses APIs.  
- Amazon Bedrock can generate API keys for integrations; the AWS token‑generator Python library derives short‑term tokens from the standard AWS CLI credential chain.

## 📍 Availability
- Kimi K3 can be added through the existing Bedrock Runtime APIs; health data can stay inside AWS and Mumbai as a fallback Region.  
- The **India‑only inference profile** (`in.moonshotai.kimi‑k3`) enforces processing within Indian Regions only.  
- Global profile (`global.moonshotai.kimi‑k3`) offers the lowest cost and broadest availability for workloads that do not require strict residency.

## 💡 Why it matters
- Enables **local workloads** that must obey strict data residency rules, such as health‑focused applications.  
- Reduces operational cost and latency through prompt caching.  
- Simplifies multimodal processing by handling image OCR and translation internally.  
- Powers real‑world agents like **Jade**, the AI health and wellness assistant in the Ultrahuman app, which fields more than **14 000 conversations a day** using personal Ring and glucose data.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22220-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22220-2-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-22220-3-1.jpg)

#KimiK3 #AmazonBedrock #AIInference #MultiModal

---

*Source: [Introducing India-based inference for Kimi K3 on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-india-based-inference-for-kimi-k3-on-amazon-bedrock/)*
