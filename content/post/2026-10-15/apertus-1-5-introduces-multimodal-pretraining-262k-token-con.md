---
title: "Apertus 1.5 Introduces Multimodal Pretraining, 262k Token Context and Thinking Mode"
slug: "apertus-1-5-introduces-multimodal-pretraining-262k-token-context-and-thinking-mode"
description: "Apertus 1.5 is a continued pretraining of the first‑generation model that adds large amounts of text and multimodal data while keeping the model fully open."
date: 2026-10-15T22:04:06+05:30
tags: [Apertus, MultimodalAI, OpenSource, LongContext]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Computer Vision", "Open Source AI"]
image: "https://cdn-uploads.huggingface.co/production/uploads/61f1877a168a0b52fda88455/2mHXxCtfos6CgwFSNKFVi.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# Apertus 1.5 Introduces Multimodal Pretraining, 262k Token Context and Thinking Mode

Apertus 1.5 is a continued pretraining of the first‑generation model that adds large amounts of text and multimodal data while keeping the model fully open.

## 🔍 Overview
- "Apertus 1.5 is a continued pretraining of the first generation model: adding 4 trillion tokens of text and multimodal training data to the 8B model and 2 trillion tokens to the 70B model, for a total of 19T and 17T, respectively."
- All releases are "fully open: open weights, open data, open values, and full training details."
- Native multimodal understanding: the models accept images and audio alongside text, "bringing documents, diagrams, and photos into the conversation."
- Spoken language is also processed, "though this remains experimental."

## 🧩 How It Works
- Multimodality is introduced in an **early‑fusion** manner: images and audio are tokenized and placed in the same sequence as text tokens, "instead of using a separate vision encoder."
- Image tokenization uses the **Emu3.5 tokenizer** (a 512×512 image → 1,024 tokens).
- Audio tokenization uses **WavTokenizer** (40 tokens per second).
- Only the vocabulary is extended, so "the architecture stays unchanged and training runs at text‑only speed."
- The models "understand images and audio but generate only text."

## ⚙️ Key Details
- **Thinking Mode** – "The models can be switched into a thinking mode to reason about the input before answering, which improves performance on reasoning problems."
- **Long Context** – Context window grows to **262,144 tokens**, a 4× increase over Apertus 1.0.
- **Improved Instruction‑Following** – Better instruction adherence than Apertus 1.0 gives more predictable and accurate responses.
- **Improved Tool Use** – Trained for better tool integration, allowing more effective use of external tools and APIs.
- **Open Values** – Stronger adherence to the Apertus Charter, providing transparency to the model’s values and principles.

## 📊 Training Pipeline
- **Pretraining Stages**
  1. *Unpaired*: text plus standalone images and audio.
  2. *Paired*: image‑caption and audio‑transcript pairs.
  3. *Cooldown*: higher‑quality data with more math and code.
  4. *Long Context*: window grows step by step from 8k to 262k tokens.
- More than half of the training tokens are text‑only, preserving the language abilities of Apertus 1.0.
- Text data refreshed with sources such as **FineWeb2‑HQ+**, **FinePDFs**, and **Nemotron‑CC**.
- All new data meets the same bar as before: publicly available, permissively licensed, and with robots.txt opt‑outs respected retroactively. Every source is listed in **apertus‑data‑transparency**.
- **Post‑training stages**: SFT → long‑context SFT → RL → DPO → charter alignment (SDPO).
  - SFT on 3.7M text samples plus image and speech data.
  - Reasoning traces added only to prompts the model can’t already solve without them.
  - Tool‑use data restricted to execution‑verified trajectories.
  - Long‑context SFT at the full 262k window restores the long‑context ability that short‑context SFT erodes.
  - RL with verifiable rewards (RLVR) on about 350k math, code, instruction‑following, multilingual, and vision prompts, mixing thinking on and off.
  - DPO with judge‑scored preference pairs improves chat quality, tool use, and safety.
- The text SFT mix, the preference pool, and the training pairs are released on Hugging Face.

## 🚀 Availability
- All weights, data, values, and full training details are released openly.
- The released assets include the text SFT mix and the preference pool used for DPO.

![Text performance plot](https://raw.githubusercontent.com/swiss-ai/model-cards-assets/main/apertus_1.5/text_performance_plot.png)
![Visual performance plot](https://raw.githubusercontent.com/swiss-ai/model-cards-assets/main/apertus_1.5/visual_performance_plot.png)

![figure](https://raw.githubusercontent.com/swiss-ai/model-cards-assets/main/apertus_1.5/text_performance_plot.png)

![figure](https://raw.githubusercontent.com/swiss-ai/model-cards-assets/main/apertus_1.5/visual_performance_plot.png)

#Apertus #MultimodalAI #OpenSource #LongContext

---

*Source: [Apertus 1.5 Release Notes](https://huggingface.co/blog/swiss-ai/apertus-v15-release-notes)*
