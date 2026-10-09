---
title: "Trajectory-Grounded Instruction Translator Boosts Aerial Navigation Success"
slug: "trajectory-grounded-instruction-translator-boosts-aerial-navigation-success"
description: "A new front‑end called the Trajectory‑Grounded Instruction Translator (TGIT) was introduced to bridge the gap between short, intent‑driven user commands and the detailed, trajectory‑aligned..."
date: 2026-10-09T18:05:31+05:30
tags: [VisionLanguageNavigation, InstructionTranslation, AIResearch]
categories: ["AI", "Machine Learning", "Robotics", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# Trajectory-Grounded Instruction Translator Boosts Aerial Navigation Success

A new front‑end called the Trajectory‑Grounded Instruction Translator (TGIT) was introduced to bridge the gap between short, intent‑driven user commands and the detailed, trajectory‑aligned instructions that aerial vision‑and‑language navigation (VLN) agents expect. TGIT translates weak, user‑friendly inputs into commands that a frozen OpenFly navigator can execute, dramatically improving success rates.

## 🔍 Overview
- Aerial VLN agents trained on detailed, trajectory‑aligned commands see their success rate (SR) drop from **31.03%** to **11.33%** when faced with short, intent‑driven instructions – an *instruction gap*.
- Prompting a language model with human‑written style examples to create paired, intent‑centered *Weak* commands yields an SR of **15.27%**.
- TGIT is a front‑end that keeps the navigator frozen while learning to translate Weak inputs based on the outcomes of its own trajectories.

## 🧩 How it works
- TGIT receives a Weak command (short, intent‑driven) from the user.
- It translates the command into a detailed instruction compatible with the frozen OpenFly navigator.
- The translator is trained by observing the navigator’s trajectory outcomes, allowing it to align translations with successful navigation behavior.

## ⚙️ Key results
- Weak‑trained TGIT raises SR for Weak inputs from **15.27%** to **37.93%**.
- Zero‑shot transfer to real human instructions improves SR from **11.33%** to **32.51%**.
- On a held‑out OpenFly split, SR increases from **4.95%** to **20.79%**.
- TGIT also yields recovery on the CityNav and AirVLN benchmarks.

| Scenario | Success Rate |
|----------|--------------|
| Detail‑rich commands (frozen OpenFly) | 31.03% |
| Short intent commands (frozen OpenFly) | 11.33% |
| Weak commands via prompted LM | 15.27% |
| Weak commands via TGIT | 37.93% |
| Real human instructions (zero‑shot TGIT) | 32.51% |
| Held‑out OpenFly (baseline) | 4.95% |
| Held‑out OpenFly (TGIT) | 20.79% |

## 📈 Impact
- Enables existing VLN navigators to handle user‑friendly instructions without retraining the core model.
- Demonstrates that trajectory‑grounded translation can close the instruction gap across multiple aerial navigation datasets.
- Provides a pathway for scalable training of translators using language models and trajectory feedback.

---

#VisionLanguageNavigation #InstructionTranslation #AIResearch

---

*Source: [Speaking the Navigator's Language: Trajectory-Grounded Instruction Translation for Frozen Aerial VLN Agents](https://arxiv.org/abs/2610.10635v1)*
*Source: [AgentHorizon: Evaluating Agentic Judges for Long-Horizon Computer-Use Tasks](https://arxiv.org/abs/2610.11050v1)*
