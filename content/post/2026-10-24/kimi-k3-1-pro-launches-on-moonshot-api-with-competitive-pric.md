---
title: "Kimi K3.1 Pro launches on Moonshot API with competitive pricing and strong benchmark scores"
slug: "kimi-k3-1-pro-launches-on-moonshot-api-with-competitive-pricing-and-strong-benchmark-scores"
description: "Kimi K3.1 Pro landed on the Kimi API today. The model is not yet available with open weights, but Moonshot has promised full weight release by November 4, 2026."
date: 2026-10-24T18:02:39+05:30
tags: [KimiAI, LLM, Benchmarks, OpenWeights]
categories: ["AI", "Machine Learning", "Large Language Models", "AI Benchmarks", "APIs"]
image: "https://static.simonwillison.net/static/2026/kimi-k3.1-card.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Kimi K3.1 Pro launches on Moonshot API with competitive pricing and strong benchmark scores

Kimi K3.1 Pro landed on the Kimi API today. The model is not yet available with open weights, but Moonshot has promised full weight release by November 4, 2026.

## 🔍 Overview
- Kimi K3.1 Pro is the latest offering from Moonshot and is positioned alongside leading frontier models such as Claude Opus 5.5 and GPT‑6 Astra.
- An “Highspeed” variant is also announced, delivering 2–3× faster inference at twice the price (input‑token‑cache‑hit pricing remains unchanged).

## ⚙️ Key details
- **Open‑weight timeline**: Full model weights slated for release on 2026‑11‑04.
- **Pricing (USD)**:
  - Input tokens: $2.00 per million tokens
  - Output tokens: $10.00 per million tokens
  - Pricing matches GPT‑6.1 Sol and is half the cost of Claude Opus 5.5.
- **Model variants**:
  - Standard Kimi K3.1 Pro
  - Highspeed version (2–3× faster, double price except for cached input tokens)

## 📈 Benchmarks
- Moonshot’s internal benchmarks place Kimi K3.1 Pro roughly on par with Claude Opus 5.5 and GPT‑6 Astra, beating them on a few tests and coming close on others.
- Independent scoring by Artificial Analysis gives Kimi a score of **55**, ahead of:
  - Claude Fable 5.1 – 53
  - GPT‑6 Astra – 53
  - Gemini 4 Argon – 53
  - and behind Claude Opus 5.5 – 58.
- This is the first time a soon‑to‑be open‑weight model has scored this highly against the current frontier.

| Model                | Score |
|----------------------|-------|
| Claude Opus 5.5      | 58    |
| Kimi K3.1 Pro        | 55    |
| Claude Fable 5.1     | 53    |
| GPT‑6 Astra          | 53    |
| Gemini 4 Argon       | 53    |

## 🛠️ How to use
The model can be accessed via the Moonshot API using an OpenAI‑compatible endpoint. Example command (run with the `llm` tool version 0.32):
```bash
llm openai endpoint \
  https://api.moonshot.ai/v1 \
  --key kimi \
  -m kimi-k3.1-pro \
  "Generate an SVG of a pelican riding a bicycle" \
  --responses \
  -o reasoning_effort low \
  > kimi-k3.1-pro-pelican-low.stdout.txt \
  2> kimi-k3.1-pro-pelican-low.stderr.txt
```
The endpoint supports three reasoning levels—low, medium, and max—producing different “pelican” outputs for each level.

## 🚀 Availability
- Kimi K3.1 Pro is now live on the Kimi API.
- Open weights are not yet released; the promised date is November 4, 2026.
- The Highspeed version will be priced at twice the standard rate, with the exception that input‑token‑cache‑hit pricing stays the same.


![figure](https://static.simonwillison.net/static/2026-10-23/image-2.png)

#KimiAI #LLM #Benchmarks #OpenWeights

---

*Source: [Introducing Kimi K3.1 Pro](https://simonwillison.net/2026/Oct/23/kimi-k31-pro/)*
