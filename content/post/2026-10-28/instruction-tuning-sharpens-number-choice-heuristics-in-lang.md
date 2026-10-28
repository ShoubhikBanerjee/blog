---
title: "Instruction Tuning Sharpens Number-Choice Heuristics in Language Models"
slug: "instruction-tuning-sharpens-number-choice-heuristics-in-language-models"
description: "'3, 7, 14, 17, 42: Instruction Tuning Installs and Sharpens Number-Choice Heuristics in Language Models' was submitted on **26 Oct 2026**. The paper investigates how instruction‑tuned checkpoints..."
date: 2026-10-28T18:02:11+05:30
tags: [instructiontuning, numberchoice, languagemodels]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Research"]
author: "Shoubhik Banerjee"
draft: false
---

# Instruction Tuning Sharpens Number-Choice Heuristics in Language Models

## 🔎 Overview
"3, 7, 14, 17, 42: Instruction Tuning Installs and Sharpens Number-Choice Heuristics in Language Models" was submitted on **26 Oct 2026**. The paper investigates how instruction‑tuned checkpoints change the way language models select integers when prompted for a random number.

## 🧪 Method
- "We measure, **without sampling error**, the probability a language model assigns to each integer from 1 to N when asked for a random number."
- "For a fixed prompt the model defines one probability vector, which we compute by **summing over each integer's scored spellings** rather than estimate by sampling, removing the noise that limits earlier studies."
- "We evaluate **18 open‑weight model lines** at five ranges up to N = 100, under 29 decoding configurations, on two inference stacks; **15 of them have matched base and instruction‑tuned checkpoints** that both give usable answers."

## ⚙️ Key Findings
- "Instruction tuning **makes the distribution less uniform** in all 15 pairs."
- "It **installs one heuristic, round‑number avoidance**, and **sharpens another, endpoint avoidance**."
- "Base checkpoints **do not avoid round numbers** once the endpoints are removed from those sets; tuned checkpoints **avoid them, multiples of 10 almost completely**."
- "Base checkpoints **return the endpoints 1 and N at 0.30 to 0.60 of the interior rate**; tuned checkpoints **almost never return them**."
- "A **preference for odd numbers** is consistent across tuned checkpoints only at N = 100, where base checkpoints also show it weakly."
- "Endpoint avoidance and the odd preference **fit the account Kubovy and Psotka [6] proposed for human number choice**; round‑number avoidance is not part of that account, and the midpoint avoidance it predicts is essentially absent, with one slight exception at N = 100."
- "Tuning does **not install a new favourite integer** shared across models: above N = 10 no modal integer is shared by more than 42 percent of tuned conditions, and **P (17) rises in 10 of 15 pairs and falls in 5**."
- "The concentration is present in the model's own distribution: at temperature 1.0, nucleus truncation at top‑p 0.95 **adds a median of 0.035 to the total variation distance**."

## 💡 Why It Matters
- The results show that **instruction tuning can embed human‑like number‑choice heuristics** (endpoint and odd‑number biases) while also introducing a distinct **round‑number avoidance** pattern not seen in human studies.
- Understanding these systematic biases is crucial for **interpreting model outputs** in applications that rely on random‑number generation or probabilistic sampling.
- The work provides a **noise‑free measurement approach** that could be reused to study other latent preferences in language models.

---
*Evidence drawn exclusively from the submitted manuscript (26 Oct 2026).*

#instructiontuning #numberchoice #languagemodels

---

*Source: [3, 7, 14, 17, 42: Instruction Tuning Installs and Sharpens Number-Choice Heuristics in Language Models](https://arxiv.org/abs/2610.36178v1)*
*Source: [Causal Localization of Evidence Effects in Transformers](https://arxiv.org/abs/2610.36524v1)*
*Source: [A Quantitative Approach to Asch Conformity in Frontier Large Language Models](https://arxiv.org/abs/2610.36668v1)*
*Source: [Language Models Keep Abandoned Analyses: Residue and Adaptation after Garden-Path Sentences](https://arxiv.org/abs/2610.36797v1)*
