---
title: "Cross‑Lingual Fairness Gaps in Homoglyph and Invisible‑Character Watermarks"
slug: "crosslingual-fairness-gaps-in-homoglyph-and-invisiblecharacter-watermarks"
description: "A new study updates our understanding of edit‑based watermarks that hide signals in text after it is written. By comparing 40 language varieties across 24 scripts, the researchers show that fairness..."
date: 2026-10-28T22:03:50+05:30
tags: [AIWatermarking, Fairness, MultilingualNLP]
categories: ["AI", "Computation And Language", "Machine Learning", "Natural Language Processing", "Ethics"]
author: "Shoubhik Banerjee"
draft: false
---

# Cross‑Lingual Fairness Gaps in Homoglyph and Invisible‑Character Watermarks

A new study updates our understanding of edit‑based watermarks that hide signals in text after it is written. By comparing 40 language varieties across 24 scripts, the researchers show that fairness gaps persist even when the watermark does not touch a tokenizer.

## 🔍 Overview
- Homoglyph and invisible‑character watermarks are *edit‑based* watermarks.
- They embed a signal **after** text generation by swapping characters for visually identical Unicode homoglyphs or inserting non‑displaying characters.
- This approach works **without any access to the model** that produced the text.
- Because the technique operates on individual characters, it never interacts with a tokenizer.

## 🧩 How it works
- The watermark replaces selected characters with homoglyphs that have different Unicode code points, or it inserts invisible characters that are not rendered.
- These modifications are invisible to readers but can be detected by a keyed detector that knows the mapping.

## ⚙️ Key findings
- Generation‑time watermarks perform less well for lower‑resource languages due to how tokenizers split text.
- The edit‑based approach sidesteps this tokenizer issue, prompting the question of whether it also avoids the fairness gap.
- Across the 40 language varieties, **capacity** (the hidden bits each character can carry) varied **3.3‑fold**.
- **Script** accounted for **96 %** of the capacity variation.
- Within the Latin script, resource level showed **no detectable difference** (ρ=+0.095, p=0.78).
- Across scripts, capacity **rises with resource level** (ρ=+0.54, 95 % CI [+0.14,+0.83]), reflecting that lower‑resource languages often use scripts with few homoglyphs.
- Ordinary copy‑paste, which strips invisible characters, widens the gap: a detector needs about **2 code points** for English or Persian but **93 code points** for Lao.
- Removing the tokenizer does **not** remove the inequity; it merely changes the source of the gap.

## 📊 Capacity and Script Effects
| Metric | Value |
|---|---|
| Capacity variation across languages | 3.3‑fold |
| Portion of variation explained by script | 96 % |
| Correlation of capacity with resource level (across scripts) | ρ=+0.54 (95 % CI [+0.14,+0.83]) |

## 💡 Why it matters
- The findings reveal that even **tokenizer‑independent** watermarks can exhibit large cross‑lingual fairness disparities.
- Practical handling of text (e.g., copy‑paste) can dramatically affect detection difficulty for some scripts.
- Understanding script‑level constraints is essential for designing equitable watermarking strategies for multilingual AI‑generated content.

*Submitted on 27 Oct 2026, Computer Science → Computation and Language.*

#AIWatermarking #Fairness #MultilingualNLP

---

*Source: [No Tokenizer, Still a Gap: Cross-Lingual Fairness of Homoglyph and Invisible-Character Watermarking](https://arxiv.org/abs/2610.36432v1)*
