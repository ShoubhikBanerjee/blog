---
title: "Z.ai launches GLM-5.3-Flash, a 320 B open‑source multimodal model"
description: "Z.ai officially launched GLM-5.3-Flash, confirming it as the previously rumored “Ox Alpha”. The model is available under an MIT license and runs fully on Chinese AI chips."
date: 2026-08-31T22:04:32+05:30
tags: [ZAI, GLM53Flash, OpenSourceAI, Multimodal, AIModels]
categories: [AI]
image: "https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-user-contents.imgix.net%2Fhttps%253A%252F%252Fcdn.qiita.com%252Fassets%252Fpublic%252Farticle-ogp-background-afbab5eb44e0b055cce1258705637a91.png%3Fixlib%3Drb-4.1.1%26w%3D1200%26blend64%3DaHR0cHM6Ly9xaWl0YS11c2VyLXByb2ZpbGUtaW1hZ2VzLmltZ2l4Lm5ldC9odHRwcyUzQSUyRiUyRmxoMy5nb29nbGV1c2VyY29udGVudC5jb20lMkZhJTJGQUNnOG9jTFdDMjVqNnl4SmNNVWlsRjJaNzhPU2xpVnpOM2ZtSllsNUZyZmZCRHFpXy1KRmpnJTNEczk2LWM_aXhsaWI9cmItNC4xLjEmYXI9MSUzQTEmZml0PWNyb3AmbWFzaz1lbGxpcHNlJmJnPUZGRkZGRiZmbT1wbmczMiZzPTI2YzNkMTkyM2I2ZjQ2MTFhMDQzMDg0ZjFmNTFmNzZh%26blend-x%3D120%26blend-y%3D467%26blend-w%3D82%26blend-h%3D82%26blend-mode%3Dnormal%26s%3D864989c61ba444ec9831520e2d51a064?ixlib=rb-4.1.1&w=1200&fm=jpg&mark64=aHR0cHM6Ly9xaWl0YS11c2VyLWNvbnRlbnRzLmltZ2l4Lm5ldC9-dGV4dD9peGxpYj1yYi00LjEuMSZ3PTk2MCZoPTMyNCZ0eHQ9TWlkbmlnaHQlMjBBSSUyMEdyb292ZSUyMDI2LTA4LTI2JnR4dC1hbGlnbj1sZWZ0JTJDdG9wJnR4dC1jb2xvcj0lMjMxRTIxMjEmdHh0LWZvbnQ9SGlyYWdpbm8lMjBTYW5zJTIwVzYmdHh0LXNpemU9NTYmdHh0LXBhZD0wJnM9NWRiODdkZThhOTVlMmY3YTQxOGQ0M2VjMWZlMDNjYTA&mark-x=120&mark-y=112&blend64=aHR0cHM6Ly9xaWl0YS11c2VyLWNvbnRlbnRzLmltZ2l4Lm5ldC9-dGV4dD9peGxpYj1yYi00LjEuMSZ3PTgzOCZoPTU4JnR4dD0lNDBtYXN5a290NTgyJnR4dC1jb2xvcj0lMjMxRTIxMjEmdHh0LWZvbnQ9SGlyYWdpbm8lMjBTYW5zJTIwVzYmdHh0LXNpemU9MzYmdHh0LXBhZD0wJnM9NTdlMTZhYmE3YzViMzE4ZTU4ZmVlMDM4YzU5NDljNGQ&blend-x=242&blend-y=480&blend-w=838&blend-h=46&blend-fit=crop&blend-crop=left%2Cbottom&blend-mode=normal&s=46f77525a385b25296a60174bc016c3d"
author: "Shoubhik Banerjee"
draft: false
---

# Z.ai launches GLM-5.3-Flash, a 320 B open‑source multimodal model

Z.ai officially launched GLM-5.3-Flash, confirming it as the previously rumored “Ox Alpha”. The model is available under an MIT license and runs fully on Chinese AI chips.

## 🔍 Overview
- GLM-5.3-Flash is a 320 B total‑parameter, 18 B active‑parameter language model.
- Context window enlarged to **1 M tokens** (initially noted as 400 k, later corrected).
- Provides native multimodal capabilities, including a vision encoder.
- Released weights, API, chat, ZCode, coding‑plan, and AutoClaw interfaces.

## 🧩 Architecture
- Employs a **Kimi Linear‑style 3:1 hybrid attention** design, called “super hybrid”.
- 34 layers of **KDA (Kimi Delta Attention)**.
- 11 layers combining **MLA (Multi‑head Latent Attention)** and **DSA (DeepSeek Sparse Attention)**.
- Utilises DeepSeek V4‑series **mHC residual paths** with four parallel streams.
- Active parameters reduced from 32 B (GLM‑5.2) to 18 B; layers from 92 to 45.
- Linear + sparse hybrid attention yields smaller per‑layer KV cache and lower compute for long‑context attention.

## ⚙️ Key Details
- **Total parameters:** 320 B
- **Active parameters:** 18 B
- **Context length:** 1 M tokens
- **License:** MIT
- **Hardware:** Runs entirely on Chinese AI chips (≈100 T tokens/day served, ≈116 k chips required for that scale).
- **Pricing:**
  - Input: $0.15 per 1 M tokens
  - Output: $0.50 per 1 M tokens
  - Cached input: ~$0.026‑0.03 per 1 M tokens (≈80 % discount)
  - Cost per task: **$0.09**
- **Cost comparison:**
  - ≈7.5× cheaper than GLM‑5.3 max ($0.68 per task)
  - ≈5.7× cheaper than GPT‑5.6 Terra (same Intelligence Index)
  - ≈4.4× cheaper than Muse Spark 1.2 (same Intelligence Index)

## 📊 Performance & Benchmarks
- **Artificial Analysis Intelligence Index:** 57 (same as GPT‑5.6 Terra and Muse Spark 1.2, 3 points below GLM‑5.3’s 60).
- Internal benchmark claims GLM‑5.3‑Flash surpasses GLM‑5.2 at all effort levels and matches Claude Opus 4.8 on coding tasks (vendor‑only benchmark).
- **Terminal‑Bench v2.1:** 84.3 % (slightly above GLM‑5.3’s 83.9 %).
- **τ³‑Banking:** 47.2 % (3.1 points lower than GLM‑5.3).
- **AA‑Omniscience score:** +7.
- **Accuracy:** 28 % (GLM‑5.3 = 34 %).
- **Hallucination rate:** 28 % (GLM‑5.3 = 30 %).
- **GDPval‑AA v2 Elo:** 1770.
- Comparable to **Grok 4.6** within error margins.

## 🚀 Availability
- Weights released on Hugging Face.
- CoreWeave announced upcoming support.
- Baseten provides day‑0 integration.
- Cline offers free integration for VS Code, JetBrains, and CLI.
- AutoClaw also supports the model.
- On launch day the chat template was updated.
- Engineer Zixuan Li advised early downloaders to re‑download.

## 📈 Adoption
- Cline recorded the fastest growth among its models, reaching **11 % of total traffic** in under a week.
- Baseten highlighted the model as **90 % cheaper than GLM‑5.2**.


![figure](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4207992%2F5ae621e4-01a6-4c9b-ae25-bdb89c54ab8e.png?ixlib=rb-4.1.1&auto=format&gif-q=60&q=75&s=4a6b35ae9bb853f447b30ac0c7e3e2ae)

#ZAI #GLM5.3Flash #OpenSourceAI #Multimodal #AIModels

---

*Source: [Midnight AI Groove 26-08-26 - Qiita](https://qiita.com/masykot582/items/1d873f9812f15a33d3b9)*
