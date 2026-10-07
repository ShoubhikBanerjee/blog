---
title: "Nemotron specialists achieve gold‑medal performance at IMO 2026 and IOI 2026"
slug: "nemotron-specialists-achieve-goldmedal-performance-at-imo-2026-and-ioi-2026"
description: "Nemotron’s adaptable foundation model was fine‑tuned and reinforced to reach gold‑medal level performance on both the International Mathematical Olympiad (IMO) 2026 and the International Olympiad in..."
date: 2026-10-07T22:09:50+05:30
tags: [Nemotron, AI, SpecialistModels, OlympiadAI]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Artificial Intelligence"]
image: "https://cdn-uploads.huggingface.co/production/uploads/67b8b0096c3182e96bf6cea1/zB6BNaB-3tiCCsnOo7gik.png"
author: "Shoubhik Banerjee"
draft: false
---

# Nemotron specialists achieve gold‑medal performance at IMO 2026 and IOI 2026

Nemotron’s adaptable foundation model was fine‑tuned and reinforced to reach gold‑medal level performance on both the International Mathematical Olympiad (IMO) 2026 and the International Olympiad in Informatics (IOI) 2026.

## 🔍 Overview
- Starting from Nemotron 3, supervised fine‑tuning (SFT), reinforcement learning (RL), and feedback‑driven inference were combined.
- The resulting systems earned gold‑medal scores at IMO 2026 (30/42 points, full credit on four of six problems) and IOI 2026 (535.4/600) under the same constraints as human contestants.
- The IOI run was a live, prospective, unofficial benchmark; the IMO proofs were graded by official IMO graders.

## 🧩 How it works
1. **Start with a strong Nemotron base model**.
2. **Curate domain‑specific problems and high‑quality reasoning traces** (e.g., 22 000 competitive‑programming problems; 414 890 proof examples across 15 818 unique problems).
3. **Apply post‑training**:
   - Supervised fine‑tuning (SFT).
   - Reinforcement learning (RL) where useful.
4. **Pair the specialist model with an inference loop** that iteratively generates candidate answers, evaluates them, and refines the best attempts (the GenCorrect generate‑evaluate‑refine strategy).
5. **Combine specialists with the general‑availability model** to leverage complementary strengths.

## ⚙️ Key details
- **Model variants**
  | Model | Total Params | Active Params | Post‑training | Points after GenCorrect |
  |-------|--------------|--------------|-------------|--------------------------|
  | Nemotron‑3‑Nano‑CC | 30 B | 3 B | SFT + RL | 468 (gold threshold 438.3) |
  | Nemotron‑3‑Ultra‑CC | 550 B | 55 B | SFT only | 502 |
  | Ultra‑CC (IOI) | – | – | – | 535.4 / 600 |
- **Training data**
  - SFT corpus: 414 890 quality‑filtered examples covering proof generation, refinement, verification, and meta‑verification.
  - RL corpus: 9 597 proof problems selected near the model’s capability frontier.
- **Performance insights**
  - Nano improved from 130 points (pre‑post‑training) → 280 after SFT → 291 after RL.
  - SFT checkpoint excelled in the first search round; RL checkpoint gave the best overall single‑checkpoint result.
  - Both checkpoints outperformed the general‑availability model in development experiments.
  - The system operated entirely in natural language, without formal provers, external tools, or internet access.

## 🚀 Availability
- Nemotron‑3‑Ultra‑CC for competitive programming is available on Hugging Face.
- The IOI paper provides the full training recipe and the GenCorrect methodology.
- Nemotron Labs IMO 2026 collection bundles the SFT and RL checkpoints, the training datasets, and Nemotron‑IMO‑Bench (200 olympiad‑level problems).

## 💡 Why it matters
- Better specialization yields stronger candidate generation, more effective critics, and higher‑quality refinements, enabling gold‑medal performance without building a new foundation model for each task.
- The live IOI run demonstrates that AI systems can compete under identical conditions to human contestants.
- The approach showcases how a single adaptable foundation can be re‑purposed for distinct, high‑stakes domains such as mathematical proof generation and competitive programming.

#Nemotron #AI #SpecialistModels #OlympiadAI

---

*Source: [One Model Family, Two Gold-Level Results: Fine-Tuning Nemotron for IOI and IMO](https://huggingface.co/blog/nvidia/nemotron-ioi-and-imo-2026)*
