---
title: "Aleph Alpha launches Kolibri: Open‑weight English‑German MoE model"
slug: "aleph-alpha-launches-kolibri-openweight-englishgerman-moe-model"
description: "German AI company Aleph Alpha released Kolibri, an open‑weight English‑German Mixture‑of‑Experts (MoE) model, on 3 October 2026."
date: 2026-10-05T18:05:56+05:30
tags: [AlephAlpha, Kolibri, OpenWeight, MoE, AIRegulation]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Governance", "European Technology"]
image: "https://localmodelwatch.tsuchitsuchi.com/wp-content/uploads/2026/10/202610031610_hackernews-49942706-en.png"
author: "Shoubhik Banerjee"
draft: false
---

# Aleph Alpha launches Kolibri: Open‑weight English‑German MoE model

German AI company Aleph Alpha released Kolibri, an open‑weight English‑German Mixture‑of‑Experts (MoE) model, on 3 October 2026.

## 🔍 Overview
- Kolibri is a 78.1 billion‑parameter MoE model with 3.46 billion active parameters per token.
- Supports English and German, targeting on‑premise deployments in German public administration, industrials, and aerospace.
- Weights are published on Hugging Face under the Apache 2.0 license.

## 🧩 How it works
- **Mixture‑of‑Experts architecture** activates only a subset of experts (3.46 B parameters) for each token, keeping inference cheap while keeping the full 78 B‑parameter model in memory.
- **UniBPE tokenizer** – a proprietary tokenizer designed for German compound words; it uses 11.2 % fewer tokens than GPT‑5 in German contexts.
- **Merlin‑Arthur protocol** trains the model to answer *“I don’t know”* when uncertain, reducing hallucinations.
- **Reasoning depth control** – users can select one of four inference‑time reasoning levels (none, low, medium, high) to balance cost and answer quality.

## ⚙️ Key details
| Attribute | Value |
|---|---|
| Total parameters | 78.1 billion |
| Active parameters per token | 3.46 billion |
| Context window | native 262 k tokens, tested up to 1 048 576 (≈ 1 million) tokens |
| VRAM requirement | ≈ 78 GB (entire model must reside in GPU memory) |
| Training data | ~24 trillion tokens ( > 20 % German ) |
| Training hardware | 768 NVIDIA B200 GPUs in Germany and Finland |
| Knowledge cutoff | 18 June 2026 |
| Reported benchmark scores | AIME 2025 96.9, GPQA Diamond 84.3, LiveCodeBench v6 85.9 |

- The model can run FP8 weights on a single NVIDIA B200 or H200 GPU.
- Despite low active‑parameter count, the full parameter set must be loaded, making personal‑laptop deployment difficult.

## 🚀 Availability
- Apache 2.0‑licensed weights are available on Hugging Face, including FP8 versions.
- No foreign ownership or control; training took place on European infrastructure.
- Community requests for 4‑bit or 8‑bit quantised builds have been voiced.

## 💡 Why it matters
- **European sovereignty**: Built to comply with the EU AI Act, GDPR, and the EU GPAI Code of Practice; announced as a sovereign AI offering for German‑language environments.
- **Technical openness**: A 189‑page technical report details model design, dataset creation, and training pipelines, praised for its tutorial‑like depth.
- **Criticisms & concerns**:
  - Performance: Dense model Qwen3.8 27B (German score 79.9) outperformed Kolibri (70.8) in official benchmarks.
  - Benchmark selection: Comparisons omitted recent lightweight MoE models such as Qwen3.8 Flash.
  - Data rights: Questions raised about copyright and IP safety of training data, including re‑phrasing using Gemma 4 and Mistral‑NeMo.
  - Ownership rumors: Reports of a possible merger or acquisition by Canadian company Cohere have sparked debate over the model’s “sovereign” status.
- **Hardware impact**: The 78 GB VRAM requirement limits use on standard laptops, prompting community exploration of quantisation and memory‑saving techniques.


![figure](https://localmodelwatch.tsuchitsuchi.com/wp-content/uploads/2026/10/202610031708_hf_model-ggml-org-GLM-5-3-Flash-GGUF-en.png)

![figure](https://localmodelwatch.tsuchitsuchi.com/wp-content/uploads/2026/10/202610031308_github_release-magnitudedev-magnitude-magnitudedev-cli-0-2-en.png)

#AlephAlpha #Kolibri #OpenWeight #MoE #AIRegulation

---

*Source: [Aleph Alpha Releases Kolibri: A New Open-Weight MoE Model | Local Model Watch](https://localmodelwatch.tsuchitsuchi.com/en/2026/10/04/aleph-alpha-kolibri-open-weight-moe/)*
*Source: [Aleph Alpha Releases Kolibri Open-Weight English-German MoE](https://zerohour.day/story/a650c74fe354cb9f07b74f64ee2a44ec35c59eab)*
