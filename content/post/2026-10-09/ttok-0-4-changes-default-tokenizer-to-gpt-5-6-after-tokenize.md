---
title: "ttok 0.4 changes default tokenizer to GPT‑5/6 after tokenizers are found identical"
slug: "ttok-0-4-changes-default-tokenizer-to-gpt5-6-after-tokenizers-are-found-identical"
description: "On 9 October 2026 the author released **ttok 0.4** and discovered that the tool was still defaulting to the GPT‑4 tokenizer. Wanting the default to reflect the newer models, the author switched it to..."
date: 2026-10-09T12:11:21+05:30
tags: [OpenAI, Tokenizer, GPT6, ttok]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Infrastructure"]
author: "Shoubhik Banerjee"
draft: false
---

# ttok 0.4 changes default tokenizer to GPT‑5/6 after tokenizers are found identical

On 9 October 2026 the author released **ttok 0.4** and discovered that the tool was still defaulting to the GPT‑4 tokenizer. Wanting the default to reflect the newer models, the author switched it to GPT‑5/GPT‑6 and used the change as a reason to ship a 1.0 version.

## 🔍 Overview
- ttok 0.4 was released on 9 Oct 2026.
- The initial default tokenizer was GPT‑4, which was considered outdated.
- The default was changed to GPT‑5/GPT‑6 to align with the latest model families.
- The change justified releasing a stable 1.0 version.

## 🧩 Tokenizer experiment
- OpenAI has not officially confirmed that GPT‑6 shares the same tokenizer as the GPT‑5 family.
- A commit by William Liu reported an experiment indicating the tokenizers are *likely* the same.
- The experiment compared **seven GPT models** (5.5, 5.6 Sol/Terra/Luna, 6 Astra/Sol/Luna).
- All models reported **44,794 tokens** and matched on **all 31 fixtures**.
- GPT‑6 showed **no input‑count change** on this corpus.

## ⚙️ Key details
- **Models tested**: 5.5, 5.6 Sol, 5.6 Terra, 5.6 Luna, 6 Astra, 6 Sol, 6 Luna
- **Token count** for each model: 44,794
- **Fixture matches**: 31/31

| Model family | Token count |
|--------------|------------|
| GPT‑5 (5.5, 5.6 variants) | 44,794 |
| GPT‑6 (Astra, Sol, Luna)   | 44,794 |

## 📅 Related timeline items
- **29 Sep 2026** – OpenAI DevDay 2026 live blog.
- **3 Oct 2026** – Comment about needing default hard‑budget caps on everything.
- **7 Oct 2026** – Claude Haiku 5.5 released.
- **9 Oct 2026** – ttok 0.4 release and default tokenizer change.

## 💡 Why it matters
- Aligning ttok’s default tokenizer with GPT‑5/6 removes the mismatch with the currently used models.
- The experiment’s results provide indirect evidence that GPT‑6’s tokenizer is identical to GPT‑5’s, simplifying tooling and budgeting for developers.
- Hard‑budget caps mentioned earlier suggest that stable token counts are important for resource planning.


#OpenAI #Tokenizer #GPT6 #ttok

---

*Source: [Release: ttok 1.0](https://simonwillison.net/2026/Oct/9/ttok/)*
