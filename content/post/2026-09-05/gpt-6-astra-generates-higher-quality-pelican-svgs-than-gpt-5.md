---
title: "GPT-6 Astra Generates Higher‑Quality Pelican SVGs Than GPT‑5.6 Models"
description: "I received access to GPT‑6 Astra and used it to generate SVG images of pelicans riding bicycles at several reasoning levels, then compared the results side‑by‑side with GPT‑5.6 models (Sol, Terra,..."
date: 2026-09-05T06:05:23+05:30
tags: [GPT6, Astra, AIComparison, CostEfficiency, SVG]
categories: [AI]
image: "https://static.simonwillison.net/static/2026/astra-grid-card.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# GPT-6 Astra Generates Higher‑Quality Pelican SVGs Than GPT‑5.6 Models

I received access to GPT‑6 Astra and used it to generate SVG images of pelicans riding bicycles at several reasoning levels, then compared the results side‑by‑side with GPT‑5.6 models (Sol, Terra, Luna).  

## 🔍 Overview
- The Pelican comparison grid for Astra was created.
- The grid includes GPT‑6 Astra images at low, medium, high, xhigh, and max reasoning levels (Astra doesn’t support reasoning=none).
- The same pelican prompt was run on GPT‑5.6 Sol, Terra, and Luna for side‑by‑side comparison.

## ⚙️ Model variants and reasoning levels
- **GPT‑6 Astra** – reasoning levels: low, medium, high, xhigh, max.
- **GPT‑5.6 Sol / Terra / Luna** – same prompt, default reasoning levels.

## 📊 Key observations
- Astra pelicans are described as “much better.”
- The very best GPT‑5.6‑Sol pelican (xhigh) is still “pretty clearly a bunch of abstract shapes.”
- Every Astra pelican from low to xhigh looks better than any GPT‑5.6‑Sol result.
- The Astra max‑level pelican is “really good,” though it sometimes fails to place legs on both sides of the frame.
- Astra low produces a better pelican than **any** GPT‑5.6‑Sol model at any level, for **9.55 cents**.
- Spending **10 cents** on any other model gets a much worse result.

## 💰 Cost and token usage
| Model | Input tokens | Input price (per million) | Output price (per million) |
|-------|--------------|---------------------------|-----------------------------|
| Astra | 16 | $10 | $50 |
| Luna  | 16 |  |  |
| Sol   | 26 | $5 | $30 |
| Terra | 26 |  |  |
- Astra’s price is roughly twice that of Sol, but it uses significantly fewer tokens, making the effective cost difference smaller.

## 🤔 Open questions
- The identical input token count for Astra and Luna leads to the comment: “I wonder if Astra and Luna are more related to each other than OpenAI let on?”

*See the grid for full quality images.*

![figure](https://static.simonwillison.net/static/2026/gpt-6-and-5-6-pelicans-html.webp)

#GPT6 #Astra #AIComparison #CostEfficiency #SVG

---

*Source: [The Pelican comparison grid for Astra is pretty interesting](https://simonwillison.net/2026/Sep/4/astra-pelicans/)*
