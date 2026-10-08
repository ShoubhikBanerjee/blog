---
title: "Anthropic launches Claude Haiku 5.5 with new pricing and subscription credits"
slug: "anthropic-launches-claude-haiku-5-5-with-new-pricing-and-subscription-credits"
description: "- Anthropic released Claude Haiku 5.5, promoted as a fast, low‑cost model."
date: 2026-10-08T22:04:21+05:30
tags: [Anthropic, ClaudeHaiku, AIpricing, LLM, APICredits]
categories: ["AI", "Machine Learning", "Large Language Models", "AI Pricing", "Cloud Services"]
image: "https://static.simonwillison.net/static/2026/claude-haiku-5-5-card.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic launches Claude Haiku 5.5 with new pricing and subscription credits

## 🔍 Overview
- Anthropic released Claude Haiku 5.5, promoted as a fast, low‑cost model.

## 💰 Pricing
| Model | Token range | Input price (per 1 M tokens) | Output price (per 1 M tokens) |
|-------|------------|-----------------------------|-------------------------------|
| Claude Haiku 5.5 | ≤ 100 k | $0.10 | $0.50 |
| Claude Haiku 5.5 | > 100 k | $0.50 | $2.50 |
| GPT‑6 Luna | ≤ 272 k | $0.10 | $0.50 |
| GPT‑6 Luna | > 272 k | $0.20 | $0.75 |
- Haiku 5.5’s base price matches OpenAI’s GPT‑6 Luna up to 100 k tokens.
- Beyond that limit Haiku 5.5’s price rises five‑fold, while Luna’s increase is less steep.

## 🧮 Tokenizer & Hidden Cost
- Haiku 5.5 uses a new, less generous tokenizer.
- The same long prompt consumes about **1.25 ×** more tokens with Haiku 5.5 than with Haiku 4.5, creating a hidden price increase.

## ⚙️ Reasoning Levels
- Haiku 5.5 defaults to **medium** reasoning and does not allow disabling reasoning.
- Example runs using the `llm` CLI:
  - **Low‑effort** pelican SVG: 0.0936 cents, 7 seconds.
  - **Max‑effort** pelican SVG (includes a reasoning trace): 3.3826 cents, 5 minutes 9 seconds.

## 📊 Comparison to Haiku 4.5
- Haiku 4.5 (which lacked reasoning levels) generated a pelican SVG for **0.7583 cents**.

## 🛠️ Tooling Improvements
- The latest `llm-anthropic` release removes the need to ship a new plugin version for each model.
  ```bash
  llm install -U llm-anthropic
  llm anthropic refresh
  llm -m claude-haiku-5.5 "Generate an SVG of a pelican riding a bicycle" -o thinking_effort low
  ```

## 📦 Additional Anthropic Updates
- Cache‑read price for Sonnet 5.5 has been halved.
- New API credit scheme (credits equal the subscription cost):
  | Plan | Monthly credit |
  |------|----------------|
  | Max 5x users | $100 |
  | Max 20x users | $200 |
  | Team subscribers | up to $500 (pooled) |
- Credits do **not** roll over; unused credits are forfeited.
- Option to disable auto‑reload for the API; requests stop when the balance runs out.

## 📈 Cost Perspective Above 100 k Tokens
- Above 100 k tokens, **GPT‑6 Luna** offers a better deal because its price increase is smaller than Haiku 5.5’s.


![figure](https://static.simonwillison.net/static/2026-10-07/haiku-5.5-max.webp)

![figure](https://static.simonwillison.net/static/2026-10-07/claude-credits.webp)

![figure](https://static.simonwillison.net/static/2025/claude-haiku-4.5-pelican.jpg)

#Anthropic #ClaudeHaiku #AIpricing #LLM #APICredits

---

*Source: [Claude Haiku 5.5](https://simonwillison.net/2026/Oct/7/claude-haiku-5-5/)*
