---
title: "Qwen3 Tajik Adaptations Show Mixed Gains on Belebele Benchmark"
slug: "qwen3-tajik-adaptations-show-mixed-gains-on-belebele-benchmark"
description: "We updated Qwen3 models with Tajik‑focused LoRA adapters, continued pretraining, and supervised fine‑tuning. The experiments lowered text loss across model sizes but produced limited and uneven..."
date: 2026-11-05T12:04:51+05:30
tags: [Tajik, LoRA, Benchmark, AIResearch]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Benchmarking", "AI Development"]
author: "Shoubhik Banerjee"
draft: false
---

# Qwen3 Tajik Adaptations Show Mixed Gains on Belebele Benchmark

We updated Qwen3 models with Tajik‑focused LoRA adapters, continued pretraining, and supervised fine‑tuning. The experiments lowered text loss across model sizes but produced limited and uneven improvements on the Belebele reading‑comprehension benchmark.

## 🔍 Overview
- Small LoRA adapters were trained on Tajik news and books for Qwen3 models ranging from 0.6 B to 8 B parameters.
- All adapters reduced Tajik text loss by **0.60 – 1.45 nats per token**.
- None of the adapters raised measured Tajik reading‑comprehension performance.

## 🛠️ Training recipe
- **LoRA adapters**: added to each model size; training data comprised Tajik news and books.
- **Continued pretraining** (8 B only): ~375 million raw Tajik tokens were ingested after the adapter stage.
- **Supervised fine‑tuning**: applied to the main model, named **e3**, after the continued pretraining.

## 📈 Results
| Model Variant | Text‑loss reduction (nats/token) | Belebele Δ accuracy (points) | English MMLU Δ (points) |
|---------------|--------------------------------|------------------------------|--------------------------|
| Qwen3‑0.6 B + LoRA | 0.60 – 1.45 | +4.2 (near chance) | – |
| Qwen3‑1.7 B + LoRA | 0.60 – 1.45 | 0 (unchanged) | – |
| Qwen3‑4 B + LoRA | 0.60 – 1.45 | –3.7 | – |
| Qwen3‑8 B + LoRA | 0.60 – 1.45 | 0 (unchanged) | – |
| Qwen3‑8 B (continued pretraining) | – | +9.9 | – |
| e3 (supervised fine‑tuning) | – | **+11.4** vs. Qwen3‑8 B | –1.2 |
| Qwen3‑0.6 B‑Base (heavy recipe) | loss close to 8 B after books‑only pretraining | near chance | –7.6 |

## ⚠️ Limitations & Issues
- The 0.6 B adapter’s +4.2‑point gain occurs while the model’s answer‑letter preference shifts, indicating no genuine comprehension.
- The 4 B adapter actually lowered accuracy by 3.7 points.
- Heavy recipe on the 0.6 B base model drove loss down but kept multiple‑choice performance near chance and hurt English MMLU by 7.6 points.
- Documentation gaps were reported: lost training records, an undocumented “thinking‑mode” dataset lacking reasoning, undocumented later branches, and a 4‑bit release missing transformer layers.

## 🤝 Openness & Community
- The work follows the values embraced by arXivLabs collaborators: openness, community, excellence, and user data privacy.
- arXiv and arXivLabs commit to partnering only with groups that uphold these principles.


#Tajik #LoRA #Benchmark #AIResearch

---

*Source: [Adapting Qwen3 to Tajik from 0.6B to 8B: Lower Text Loss Did Not Mean Better Understanding](https://arxiv.org/abs/2611.06062v1)*
