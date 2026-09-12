---
title: "MIT AI Gateway Updates with Expanded Provider Catalog and Token Compression"
slug: "mit-ai-gateway-updates-with-expanded-provider-catalog-and-token-compression"
description: "The MIT AI gateway has provided updates to its single-endpoint access system, which connects users to a vast array of AI providers and models."
date: 2026-09-12T18:03:09+05:30
tags: [MIT, AIGateway, LLM, OpenSource]
categories: ["AI", "Artificial Intelligence", "Software Development", "Cloud Infrastructure"]
image: "https://avatars.githubusercontent.com/u/8016841?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# MIT AI Gateway Updates with Expanded Provider Catalog and Token Compression

The MIT AI gateway has provided updates to its single-endpoint access system, which connects users to a vast array of AI providers and models.

## 🔍 Overview
Built by over 550 contributors, the gateway provides a single endpoint to access 352 providers and 1,312 unique chat model IDs, including Kimi, Claude, GPT, Gemini, GLM, DeepSeek, and MiniMax.

## ⚙️ Key details
* **Free Access:** 150+ providers offer free tiers, with 444 cataloged free-tier entries across 34 recurring pool keys.
* **Token Volume:** The system maintains ~1.47B free tokens per month, which can reach ~2.10B in the first month including signup credits.
* **Token Savings:** RTK and Caveman stacked compression saves between 15% and 95% of tokens, with an average saving of ~89%.
* **Routing and Scheduling:** The system features 19 routing strategies and new quota-aware scheduling called Quota-Share.
* **Compatibility:** The gateway works with Claude Code, Codex, Cursor, OpenCode, Cline, Copilot, and Antigravity.

## 🧩 How it works
| Feature | Description |
| :--- | :--- |
| OmniRoute | Catalogs free-tier entries and computes token headlines from 16 pools with published positive monthly budgets. |
| Modality Bridge | New support for vision, audio, and video. |
| Radar Free Catalog | A new opt-in catalog for free tiers. |
| Auto-fallback | Quota-aware system that switches providers to prevent hitting limits. |
| Regional Identity Check | Quotas requiring regional identity verification (e.g., ModelScope) are shown separately and not summed into the main headline. |

## 💡 Why it matters
Users can start at $0 and access a wide range of models through a single endpoint. The system includes a terms-risk catalog marking 13 providers to avoid, and figures are re-audited every two weeks against the live catalog to ensure accuracy. The results remain visible on the /dashboard/free-tiers dashboard.

#MIT #AIGateway #LLM #OpenSource

---

*Source: [diegosouzapw/OmniRoute](https://github.com/diegosouzapw/OmniRoute)*
