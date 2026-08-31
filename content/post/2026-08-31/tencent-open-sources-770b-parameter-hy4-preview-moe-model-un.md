---
title: "Tencent open-sources 770B parameter Hy4 preview MoE model under Apache 2.0"
description: "Tencent's Hunyuan team open-sourced Hy4 preview, a 770 billion parameter mixture-of-experts (MoE) model, on August 28, 2026. The release marks a significant development in accessible large-scale AI."
date: 2026-08-31T18:56:17+05:30
tags: [Tencent, Hy4, OpenSource, AIModels, MixtureOfExperts]
categories: [AI]
image: "https://oukdqujzonxvqhiefdsv.supabase.co/storage/v1/object/public/blogs/3f0b19f5-4aad-45d7-a724-c5f22fd85742.png"
author: "Shoubhik Banerjee"
draft: false
---

# Tencent open-sources 770B parameter Hy4 preview MoE model under Apache 2.0

Tencent's Hunyuan team open-sourced Hy4 preview, a 770 billion parameter mixture-of-experts (MoE) model, on August 28, 2026. The release marks a significant development in accessible large-scale AI. 

## 🔍 Overview
Hy4 preview activates 49 billion parameters per token across 256 routed experts plus one shared expert, while maintaining a 1 million token context window. It is optimized for engineering tasks, as demonstrated through benchmark performance and human evaluations.

## 🧩 Model Architecture
- **Total parameters**: 770 billion
- **Active parameters per token**: 49 billion
- **Experts**: 256 routed + 1 shared
- **Context window**: 1 million tokens
- **Precision variants**: FP8 (quantized) available alongside base weights

## ⚙️ Key Technical Details
- **License**: Apache 2.0 (no commercial restrictions)
- **Benchmarks**: Scores 92.3 on GPQA Diamond and 65.7 on SWE-bench Pro
- **API Pricing**: $0.834 per million input tokens, $2.501 per million output tokens
- **Human Evaluation**: Scored 2.99/4 in Tencent's blind assessment by 163 experts across 203 engineering tasks, outperforming GLM-5.3 (2.92) and Kimi K3 (2.94)

## 🚀 Availability
- Weights hosted on Hugging Face with FP8 quantized version
- Pre-built Docker recipes for vLLM and SGLang inference
- Immediate accessibility eliminates typical community porting delays

## 💡 Why It Matters
- **Unprecedented licensing**: First 700B+ parameter model under permissive Apache 2.0
- **Efficiency**: FP8 optimization enables deployment on single high-memory servers
- **Performance**: Matches specialized models in blind engineering evaluations
- **Contrast with competitors**: Released alongside Ant Group's Ling-3.0-Flash (MIT license, 124B params, 5.1B active per token) but offers significantly higher activation density

## 🌐 Comparative Open-Source Models
| Model          | Total Parameters | Active per Token | Context Window | License     |
|----------------|------------------|------------------|----------------|-------------|
| Hy4 Preview    | 770B             | 49B              | 1M tokens      | Apache 2.0  |
| Ling-3.0-Flash | 124B             | 5.1B             | 256K tokens    | MIT         |


#Tencent #Hy4 #OpenSource #AIModels #MixtureOfExperts

---

*Source: [Tencent Opens a 770B Model Under Apache 2.0: AI News Aug 31](https://www.buildfastwithai.com/blogs/tencent-opens-a-770b-model-under-apache-2-0-ai-news-aug-31)*
