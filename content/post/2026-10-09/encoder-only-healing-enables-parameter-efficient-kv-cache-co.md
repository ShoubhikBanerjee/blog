---
title: "Encoder‑Only Healing Enables Parameter‑Efficient KV‑Cache Compression"
slug: "encoderonly-healing-enables-parameterefficient-kvcache-compression"
description: "A new study shows that fine‑tuning only the encoder after post‑hoc SVD‑based KV‑cache compression matches full‑factor healing while using far fewer trainable parameters and optimizer memory."
date: 2026-10-09T18:05:31+05:30
tags: [KVCache, ParameterEfficient, ModelCompression, FineTuning]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Model Compression"]
author: "Shoubhik Banerjee"
draft: false
---

# Encoder‑Only Healing Enables Parameter‑Efficient KV‑Cache Compression

A new study shows that fine‑tuning only the encoder after post‑hoc SVD‑based KV‑cache compression matches full‑factor healing while using far fewer trainable parameters and optimizer memory.

## 🔍 Overview
- The paper *Freeze the Decoder, Heal the Encoder* (submitted 25 Sep 2026) investigates parameter‑efficient fine‑tuning recipes for KV‑cache compression.
- It reveals that comparing recipes with a shared learning rate can create a misleading advantage for smaller‑parameter arms.
- By assigning individual learning rates to each factor, the apparent win of encoder‑only healing disappears, exposing true parity.

## 🧩 How It Works
1. **Low‑rank cache conversion** – An already‑pretrained model’s key/value weights are factorized into:
   - a down‑projection (**encoder**) and
   - an up‑projection (**decoder**) forming a low‑rank, multi‑head‑latent‑attention‑style cache.
2. **Healing fine‑tune** – A short fine‑tune (“healing”) is applied to recover accuracy lost to truncation.
3. **Learning‑rate strategy** – Instead of a single shared rate, each factor receives its own tuned learning rate.

## ⚙️ Key Findings
- **Shared learning rate bias**: When arms differ in trainable‑parameter count, a common learning rate depresses larger arms’ means and inflates variance, fabricating a multi‑seed‑significant advantage for the smallest arm.
- **Encoder‑only healing parity**: With per‑arm learning‑rate tuning, healing only the encoder achieves the same accuracy as healing the decoder or both factors.
- **Resource savings**:
  - **3× fewer trainable parameters**
  - **3× less optimizer‑state memory**
- **Empirical verification**:
  - Tested on the vision‑language model **Qwen2.5‑VL‑3B‑Instruct** with three random seeds per configuration.
  - Replicated on a text‑only testbed across two backbones.
- **Practical recipe**: Encoder‑only healing is a lower‑memory drop‑in method for retrofitting low‑rank KV‑cache compression during training.

## 🚀 Why It Matters
- Provides a **memory‑efficient** path to enable low‑rank KV‑cache compression without sacrificing model performance.
- Highlights the **importance of per‑arm learning‑rate tuning** when comparing fine‑tuning strategies that differ in parameter count, a caution applicable beyond this specific setting.

## 💡 Takeaway
For practitioners seeking to compress KV caches, applying a short healing phase to the encoder alone—while tuning its learning rate separately—delivers parity with full‑factor approaches at a fraction of the memory cost.

#KVCache #ParameterEfficient #ModelCompression #FineTuning

---

*Source: [Freeze the Decoder, Heal the Encoder: Parameter-Efficient Adaptation for SVD-Based KV-Cache Compression](https://arxiv.org/abs/2610.10552v1)*
*Source: [Lossy Compressive Text Autoencoders](https://arxiv.org/abs/2610.10738v1)*
*Source: [Sparse Attention Is Matrix Approximation, Not Choosing from a Bag of Values](https://arxiv.org/abs/2610.10871v1)*
*Source: [SFT-as-Context Mitigates Forgetting in Supervised Fine-Tuning](https://arxiv.org/abs/2610.11132v1)*
*Source: [REMORY: Learning Residual Memory for Context Compaction](https://arxiv.org/abs/2610.11287v1)*
