---
title: "Roundup of 12 AI API Endpoints and Their Supported Models"
slug: "roundup-of-12-ai-api-endpoints-and-their-supported-models"
description: "This post compiles details on 12 different AI API service endpoints, including their base URLs, rate limits, tips for usage, and the specific model variants available for each."
date: 2026-11-28T22:07:57+05:30
tags: [APIs, LLM, DeveloperTools, AIModels, Endpoints]
categories: ["AI", "APIs", "Developer Tools", "Large Language Models", "AI Infrastructure"]
image: "https://avatars.githubusercontent.com/u/101497510?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Roundup of 12 AI API Endpoints and Their Supported Models

This post compiles details on 12 different AI API service endpoints, including their base URLs, rate limits, tips for usage, and the specific model variants available for each.

## 🧩 Endpoint Details

The following table lists each API service, its endpoint URL, and any stated rate limits or usage tips found in the evidence. Note that not all services provided rate limit or tip information.

| Service | API Endpoint | Rate Limits / Tips |
| :--- | :--- | :--- |
| Agens AI | https://apihub.agnes-ai.com/v1 | None stated |
| AI BBS 中转 | https://ai.bbs.lc/v1 | Limits From Upstream Service; Tip: Key选择「免费」分组 / Create key in the "免费" group |
| Bigmodel | https://open.bigmodel.cn/api/paas/v4/ | None stated |
| ChatAnywhere | https://api.chatanywhere.tech | 100 Points Per Day + 50000 Points Per Week + ... |
| Cohere | https://api.cohere.ai/compatibility/v1 | RPM 20 \| RP/Mo 1000; Tip: 绑定支付方式可以使用速率限制更宽松的 Production Key / Binding payment methods can use rate limiting and relaxed Production Key |
| FreeAIapikey | https://api.freeaiapikey.com/v1 | TPD 100000 |
| G4F | https://g4f.space/v1 | None stated |
| Google Gemini | https://generativelanguage.googleapis.com/v1beta/openai | None stated |
| Groq | https://api.groq.com/openai/v1/ | RPM 30 \| RPD 1000 |
| Hanzo | https://api.hanzo.ai/v1 | Free plan daily request pool |
| HuggingFace | https://router.huggingface.co/v1 | $0.10 monthly credit |
| Intern AI | https://chat.intern-ai.org.cn/api/v1 | Tip: 密钥有效期 6 个月 / The key is valid for 6 months |

## ⚙️ Supported Models

Below is a list of the model identifiers associated with each API endpoint in the evidence. The lists reflect only the exact model names provided for each service.

- **Agens AI**: agnes-2.0-flash, agnes-2.5-flash, agnes-3.0-flash
- **AI BBS 中转**: deepseek-flash, deepseek-v4-pro
- **Bigmodel**: GLM-4.6V-Flash, GLM-4.7-Flash
- **ChatAnywhere**: deepseek-chat, deepseek-v3.2, deepseek-v4-pro, deepseek-v4.1-flash, deepseek-v4.1-flash-1017, gpt-3.5-turbo, gpt-4.1, gpt-4.1-mini, gpt-4o, gpt-4o-mini, gpt-5, gpt-5-mini, gpt-5-nano, gpt-5.1, gpt-5.2, gpt-5.4, gpt-5.4-mini, gpt-5.4-nano, gpt-5.5, gpt-5.6-luna, gpt-5.6-sol, gpt-5.6-terra, gpt-6-astra, gpt-6-luna, gpt-6-sol, gpt-6.1-sol, gpt-6.1-terra, gpt-6.2-astra, gpt-6.2-sol
- **Cohere**: c4ai-aya-expanse-32b, c4ai-aya-vision-32b, command-a-03-2025, command-a-plus-05-2026, command-a-reasoning-08-2025, command-a-translate-08-2025, command-a-vision-07-2025, command-r-08-2024, command-r-plus-08-2024, command-r7b-12-2024, command-r7b-arabic-02-2025, north-mini-code-1-0, north-mini-code-1.0, north-small-translate-1.0, north-small-translate-09-2026, tiny-aya-earth, tiny-aya-fire, tiny-aya-global, tiny-aya-water
- **FreeAIapikey**: anthropic/claude-fable-5.1, anthropic/claude-opus-4.7, anthropic/claude-opus-4.8, anthropic/claude-opus-5, anthropic/claude-opus-5.5, anthropic/claude-sonnet-5, anthropic/claude-sonnet-5.5, MoonshotAI/kimi-k3, MoonshotAI/kimi-k3.1-pro, openai/gpt-5.6-sol, openai/gpt-6-Astra, openai/gpt-6-sol, openai/gpt-6.1-sol, openai/gpt-6.2-sol
- **G4F**: auto
- **Google Gemini**: gemini-3-flash-preview, gemini-3.5-flash, gemini-3.6-flash, gemini-3.7-flash, gemini-3.1-flash-lite-preview, gemini-3.5-flash-lite, gemma-4-26b-a4b-it, gemma-4-31b-it
- **Groq**: allam-2-7b, llama-3.1-8b-instant, llama-3.3-70b-versatile, openai/gpt-oss-20b, openai/gpt-oss-120b, qwen/qwen3.6-27b, qwen/qwen3.8-27b
- **Hanzo**: bolt, hanzo/zen, kimi-k3.1-pro, minimaxai/minimax-m3.1-flash, mistralai/mistral-large-4-1t-a52b, moonshotai/kimi-k3.1-pro, nvidia/nemotron-3-ultra-550b-a55b, nvidia/nemotron-3.5-bolt-e4b, nvidia/nemotron-3.5-lightning-30b-a3b, nvidia/nemotron-3.5-super-vl-120b-a12b, zen-bolt, zen-coder, zen-vl
- **HuggingFace**: deepseek-ai/DeepSeek-V4.1-Flash, inclusionAI/Ling-3.1-flash, meta-models/Muse-Glimmer-30B, moonshotai/Kimi-K3, nvidia/NVIDIA-Nemotron-3.5-Super-VL-120B-A12B-NVFP4, Qwen/Qwen3.8-27B, Qwen/Qwen3.8-Flash-Next, xingchen-agi/xing4.0-29b-a4b:free, zai-org/GLM-5.3, zai-org/GLM-5.3-Flash
- **Intern AI**: intern-latest

#APIs #LLM #DeveloperTools #AIModels #Endpoints

---

*Source: [for-the-zero/Free-LLM-Collection](https://github.com/for-the-zero/Free-LLM-Collection)*
