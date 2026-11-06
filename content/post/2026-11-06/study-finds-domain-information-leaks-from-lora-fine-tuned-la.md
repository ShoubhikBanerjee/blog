---
title: "Study Finds Domain Information Leaks from LoRA‑Fine‑Tuned Language Models"
slug: "study-finds-domain-information-leaks-from-lorafinetuned-language-models"
description: "A new study investigates how much of the training‑data domain can be inferred from a LoRA‑fine‑tuned language model without ever seeing the original data."
date: 2026-11-06T18:03:32+05:30
tags: [LoRA, DomainLeakage, ModelAnalysis, AIPrivacy]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Safety", "Privacy"]
author: "Shoubhik Banerjee"
draft: false
---

# Study Finds Domain Information Leaks from LoRA‑Fine‑Tuned Language Models

A new study investigates how much of the training‑data domain can be inferred from a LoRA‑fine‑tuned language model without ever seeing the original data.

## 🔍 Overview
- Researchers fine‑tuned the base model **Qwen3.5‑0.8B** with Low‑Rank Adaptation (LoRA).
- 36 fine‑tunes were created from **18 public datasets** spanning **five domains**: medical, code, mathematics, non‑English text, and narrative prose.
- The goal was to see whether a simple classifier can recover the fine‑tune’s domain using only model artifacts.

## 🧩 How it works
- Three families of features were extracted at decreasing levels of access:
  - **White‑box**: weight‑delta statistics.
  - **Gray‑box**: internal activations on a fixed probe set.
  - **Black‑box**: model outputs (generated text).
- A **leave‑one‑dataset‑out (LODO)** protocol—frozen before any results were observed—tested domain identification on a previously unseen dataset.

## ⚙️ Key results
| Feature family | Domain accuracy |
|----------------|-----------------|
| White‑box weights | 42% |
| Gray‑box activations | 61% |
| Black‑box outputs (generated text) | 64% |
- Chance accuracy is 20%; all three families perform well above chance.
- The pre‑registered hypothesis that signal would decay from weights → activations → outputs was **contradicted**: activations and outputs were more informative than weight statistics.
- Using only generated text (without token probabilities) yields the same 64% accuracy.
- Accuracy remains stable when a third run per dataset is trained on an independently drawn subsample, and black‑box predictions are unaffected by LoRA rank (8‑64).

## 📦 Availability
- All code and per‑run feature vectors have been released.

## 💡 Why it matters
- The findings show that **domain information can leak** from LoRA‑fine‑tuned models through both internal activations and generated text.
- This has implications for privacy and the need to understand what artifacts reveal about training data.


#LoRA #DomainLeakage #ModelAnalysis #AIPrivacy

---

*Source: [Embedding-Space Fingerprinting of LoRA Fine-Tunes: Recovering the Training-Data Domain from the Model Artifact Alone](https://arxiv.org/abs/2611.07610v1)*
