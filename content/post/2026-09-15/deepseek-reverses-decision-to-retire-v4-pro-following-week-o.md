---
title: "DeepSeek Reverses Decision to Retire V4 Pro Following Week of Routing Drama"
slug: "deepseek-reverses-decision-to-retire-v4-pro-following-week-of-routing-drama"
description: "On September 11, DeepSeek reversed its decision to retire its DeepSeek V4 Pro open-weights model, officially committing to continue serving the model at unchanged billing rates. This decision follows..."
date: 2026-09-15T12:03:19+05:30
tags: [DeepSeek, xAI, Grok, OpenWeights, AIModels]
categories: ["AI", "Artificial Intelligence", "Generative AI", "AI Infrastructure"]
image: "https://cms.orcarouter.ai/api/media/file/1-938-1200x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# DeepSeek Reverses Decision to Retire V4 Pro Following Week of Routing Drama

On September 11, DeepSeek reversed its decision to retire its DeepSeek V4 Pro open-weights model, officially committing to continue serving the model at unchanged billing rates. This decision follows a week of retirement drama starting September 8, where the model was initially put on a retirement path to be replaced by V4.1 Flash. The reversal secures DeepSeek V4 Pro's position as a key text-only competitor to xAI's proprietary Grok 4.6 flagship.

## 🔍 Overview

During the week of September 8, DeepSeek placed V4 Pro on a retirement path. Under the initial plan, starting September 14, requests to `deepseek-v4-pro` were to be routed to V4.1 Flash and billed at Flash prices until a V4.1 Pro model was shipped. 

After delaying the cutoff, DeepSeek completely reversed its decision on September 11. The company has now committed to keep serving V4 Pro with unchanged billing, promising to provide notice if this ever changes. As of September 15, the model remains active with a written promise to stay.

## ⚙️ Key details

Both Grok 4.6 (released August 12, 2026) and DeepSeek V4 Pro (released August 13, 2026) are strong reasoning models with comparable independent scores. However, they represent entirely different product philosophies and technical capabilities:

| Feature | Grok 4.6 | DeepSeek V4 Pro |
| :--- | :--- | :--- |
| **Model Type** | Proprietary flagship | MIT open-weights |
| **Pricing (per 1M tokens)** | $2.00 input / $6.00 output | $0.66 / $1.98 off-peak ($1.32 / $3.96 peak) |
| **Intelligence Index Score** | 44 (Ranked #20 of 200) | 36 (Ranked #7 of 113 in class) |
| **Generation Speed** | ~57 tokens/sec | ~81 tokens/sec |
| **Context Window** | 500K | 1M |
| **Input Capabilities** | Text and image | Text-only |
| **Access Method** | xAI API or partner | Download weights or API |

Grok 4.6 leads by eight points on the independent Artificial Analysis Intelligence Index. The premium price for Grok 4.6 buys access to xAI's ecosystem, image input capability, and a 500K context served by a company focused entirely on that product.

## 🚀 Availability

Both models are active and accessible today:
* **Grok 4.6** can be called through xAI's API or a partner.
* **DeepSeek V4 Pro** weights can be downloaded under the MIT license to serve yourself, or called via API.
* **OrcaRouter Integration:** Both Grok 4.6 and DeepSeek V4 Pro route through OrcaRouter, allowing developers to call either or both models on a single key with provider list prices passed through at zero markup.

## 💡 Why it matters

This development highlights a clear split in the frontier AI model market depending on your specific infrastructure needs:

* **For Multimodal and Ecosystem-Locked Workloads:** If you want a frontier reasoning model with image input, a long context, and no interest in running your own weights, Grok 4.6's $2/$6 pricing represents fair value for its competitive index rank of 44.
* **For Text-Only, Token-Heavy Workloads:** DeepSeek V4 Pro is the highly optimized alternative for nearly every billing-related metric. It is roughly three times cheaper at peak, offers a deeper cache discount, delivers faster output, provides twice the context window, and gives you open weights as an escape hatch. Having survived its brief retirement path, it remains the open-weights option with a written promise to stay.

#DeepSeek #xAI #Grok #OpenWeights #AIModels

---

*Source: [DeepSeek V4 Pro vs Grok 4.6: The Price War, Re-Run](https://www.orcarouter.ai/blog/deepseek-pro-vs-grok-4-6)*
