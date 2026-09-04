---
title: "Sequence-to-sequence models improve Tamil spell and grammar correction"
description: "Tamil spell and grammar correction, a long‑standing challenge due to the language’s agglutinative structure and rich morphology, sees its first end‑to‑end results with fine‑tuned seq2seq models."
date: 2026-09-04T18:05:55+05:30
tags: [TamilAI, GrammarCorrection, Seq2Seq, LowResourceNLP, mBART]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Sequence-to-sequence models improve Tamil spell and grammar correction

Tamil spell and grammar correction, a long‑standing challenge due to the language’s agglutinative structure and rich morphology, sees its first end‑to‑end results with fine‑tuned seq2seq models.

## 🔍 Overview
- Tamil is an agglutinative low‑resource language with rich verbal morphology, complex sandhi (phonetic transformation) rules at word boundaries, and a script of 247 distinct letters.  
- Prior work focused on word‑level surface errors using rule‑based methods, statistical n‑gram models, Minimum Edit Distance, or hybrid pipelines with a transformer re‑ranker, but these approaches struggle with contextual errors such as subject‑verb agreement, tense consistency, or cross‑word sandhi.

## 🧩 How it works
- We reformulate correction as an end‑to‑end sequence‑to‑sequence task and fine‑tune two multilingual backbones: **mT5‑small** and **mBART‑50**.
- Training data consist of a synthetic corpus of up to **657,720** noisy‑clean Tamil sentence pairs covering ten error categories.
- Both backbones follow a **four‑stage progressive schedule** that introduces increasingly difficult error types:
  - v2 – surface noise
  - v3 – contextual grammar
  - v4 – single‑site sandhi
  - v5 – multi‑site cross‑word sandhi

| Model | Version | Targeted weakness |
|-------|---------|-------------------|
| mT5‑small | v2‑v5 | surface noise → contextual grammar → single‑site sandhi → multi‑site sandhi |
| mBART‑50 | v2‑v5 | surface noise → contextual grammar → single‑site sandhi → multi‑site sandhi |

## ⚙️ Key details
- Evaluation uses a **1,000‑sentence balanced diagnostic set** that is verified disjoint from all training data.
- **Best result:** mBART‑50 v5 achieves **69.3 %** top‑1 exact‑match accuracy, **87.5 %** on sandhi corrections, and **43.5 %** on subject‑verb agreement.
- The progressive schedule drives the gains:
  - Subject‑verb agreement accuracy rises from **1.0 %** to **52.5 %** once contextual pairs are introduced (v3).
  - Sandhi accuracy climbs from **0 %** to **87.5 %** once multi‑site sandhi pairs are added (v5).
- A precision‑recall trade‑off is observed: improving sandhi recall comes at the cost of overall identity (exact‑match) accuracy, a relationship not previously reported in the literature.

## 🚀 Availability of instruction‑tuned models
- A Tamil‑adapted instruction model, **Tamil‑LLaMA‑7B‑Instruct**, reaches **19.0 %** zero‑shot accuracy and **24.7 %** with three demonstrations, only slightly above a **20.0 %** copy baseline.  This shows that without task‑specific supervision, a Tamil‑adapted instruction model does not transfer effectively to specialized sentence‑level correction.

## 💡 Why it matters
- Demonstrates that a carefully staged seq2seq fine‑tuning regime can overcome the limitations of earlier word‑level approaches.
- Provides the first quantified trade‑off between sandhi recall and overall correction precision for Tamil.
- Highlights the need for dedicated correction supervision even for large instruction‑tuned models in low‑resource languages.

#TamilAI #GrammarCorrection #Seq2Seq #LowResourceNLP #mBART

---

*Source: [Contextual Tamil Spelling and Grammar Correction Using Progressively Fine-Tuned Sequence-to-Sequence Transformers](https://arxiv.org/abs/2609.03273v1)*
