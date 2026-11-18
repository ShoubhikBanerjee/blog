---
title: "OpenAI introduces GPT-6.2 Astra and Sol models with updated pricing"
slug: "openai-introduces-gpt-6-2-astra-and-sol-models-with-updated-pricing"
description: "OpenAI has introduced two new frontier models: GPT-6.2 Astra, designed for the hardest projects, and GPT-6.2 Sol, an efficient and versatile model for everyday work. These models are now available..."
date: 2026-11-18T22:09:17+05:30
tags: [OpenAI, GPT62, API, Pricing, Benchmarks]
categories: ["AI", "Artificial Intelligence", "Model Pricing", "Developer Tools"]
image: "https://static.simonwillison.net/static/2026/astra-6-2-max.webp"
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI introduces GPT-6.2 Astra and Sol models with updated pricing

OpenAI has introduced two new frontier models: GPT-6.2 Astra, designed for the hardest projects, and GPT-6.2 Sol, an efficient and versatile model for everyday work. These models are now available via API as `gpt-6.2-astra` and `gpt-6.2-sol`, with support included in LLM 0.38.

## 🚀 Availability

The new models have been integrated into the OpenAI API and related developer tools:

- Available in the API as `gpt-6.2-astra` and `gpt-6.2-sol`.
- Support was shipped in LLM 0.38.
- The models can be accessed using the Codex CLI and Codex desktop app with "Ultra" effort levels.

## ⚙️ Key details

Pricing for the new models reflects significant discounts compared to their predecessors. GPT-6.2 Astra is priced at 80% of the cost of the previous 6 Astra model, while GPT-6.2 Sol maintains the same pricing structure as previous Sol versions.

| Model | Input Price (per MTok) | Output Price (per MTok) | Cached Price (per MTok) |
| :--- | :--- | :--- | :--- |
| GPT-6.2 Astra | $8 | $40 | $0.40 |
| GPT-6.2 Sol | $2 | $10 | Not specified |

### Performance and User Experience

- **Benchmarks:** GPT-6.2 Astra is not scoring quite as high as Claude Fable 5.2 on various benchmarks.
- **Coding Tasks:** In a specific three.js animation task prompting a mech to stomp around Manhattan, Queens, and Brooklyn, neither GPT-6.2 Astra nor Sol performed as well as Claude Fable 5.2 and Gemini 4 Carbon in morphing Yonkers into a big mech.
- **Communication Style:** Users have reported that GPT-6.2 Astra's communication style can be confusing. Theo Browne noted that the model can pull in subagents and manage them well but may ask users "weird internal implementation detail" questions they cannot understand, such as asking if a specific reviewer writes clips to `24_g521.mp4` or `24_p11.mp4` while working on a game level.

![figure](https://static.simonwillison.net/static/2026/gpt-6-2-grid.webp)

#OpenAI #GPT-6.2 #API #Pricing #Benchmarks

---

*Source: [GPT‑6.2 Astra and GPT‑6.2 Sol](https://simonwillison.net/2026/Nov/17/gpt62-astra-and-sol/)*
