---
title: "Aleph Alpha Releases Kolibri Open-Weight Bilingual Model for Sovereign Operations"
slug: "aleph-alpha-releases-kolibri-open-weight-bilingual-model-for-sovereign-operations"
description: "Aleph Alpha has released Kolibri, an open-weight bilingual Mixture-of-Experts model designed for sovereign, mission-critical work in government and regulated industries. Building on the earlier..."
date: 2026-10-04T22:04:46+05:30
tags: [AlephAlpha, Kolibri, OpenWeight, BilingualAI, AISovereignty]
categories: ["AI", "Natural Language Processing", "Machine Learning", "Open Source AI"]
image: "https://storage.ghost.io/c/2a/1b/2a1b1782-8506-4d7d-bf53-ad3fb52e2a0f/content/images/2026/10/00-cover.Du35XCGh_ZBjCLW-1.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Aleph Alpha Releases Kolibri Open-Weight Bilingual Model for Sovereign Operations

Aleph Alpha has released Kolibri, an open-weight bilingual Mixture-of-Experts model designed for sovereign, mission-critical work in government and regulated industries. Building on the earlier Kolibri Origin and the company's automated Model Factory, this new development is optimized for English and German and supports on-premises deployment to protect internal data.

## 🔍 Overview
* **Bilingual Focus:** Optimized for English and German, with German accounting for 21.3% of pre-training tokens.
* **Open Access:** Full weights available on Hugging Face under the Apache 2.0 license.
* **Target Industries:** Specialized for public administration, automotive, semiconductors, industrial technology, and aerospace.
* **Deployment:** Customers can run the model on-premises to avoid sending internal data to third-party services.

## 🧩 How it works
Kolibri utilizes a Mixture-of-Experts (MoE) Transformer architecture and a unique attention mechanism to balance performance with inference costs. 

* **Parameters:** 78.1 billion total parameters, with 3.46 billion active per token.
* **Expert Structure:** 384 experts with six active per token.
* **Attention Layers:** Full attention is used in 10 of 50 layers, while the remaining 40 use a 512-token sliding window.
* **Training:** Developed in Germany and trained in Germany and Finland on 768 B200 GPUs. It was trained on nearly 24 trillion tokens over a 21-day initial period followed by mid-training and long-context adaptation.
* **Grounding:** Trained using the Merlin-Arthur procedure and abstention examples, teaching the model to withhold answers when evidence is absent.

## ⚙️ Key details
| Category | Metric / Feature |
| :--- | :--- |
| Context Support | Up to 1,048,576 tokens |
| English Overall Score | 75.5 |
| German Overall Score | 70.8 |
| AIME 2025 | 96.9 |
| LiveCodeBench v6 | 85.9 |
| BFCL v4 Overall | 61.4 |
| Vocabulary | 128,000-entry bilingual vocabulary designed to preserve German compounds |
| Reasoning Settings | Four options: none, low, medium, and high |

## 🚀 Availability
Kolibri is available for download on Hugging Face. For deployment, Aleph Alpha provides an inference package and a Kolibri-specific vLLM plugin, along with documented reasoning and tool-call parsers.

## 💡 Why it matters
Aleph Alpha states that Kolibri sits on the quality-versus-serving-cost Pareto frontier in both English and German. It is designed to match models with up to four times as many active parameters on math, code, grounding, and agentic tasks. By controlling the data curation, training, and evaluation within Europe, the model is intended to meet strict European compliance and sovereignty requirements.

![figure](https://storage.ghost.io/c/2a/1b/2a1b1782-8506-4d7d-bf53-ad3fb52e2a0f/content/images/2026/10/Kolibri-A-Sovereign-European-Model-on-the-Pareto-Frontier-10-03-2026_08_05_PM.jpg)

![figure](https://storage.ghost.io/c/2a/1b/2a1b1782-8506-4d7d-bf53-ad3fb52e2a0f/content/images/size/w2000/2026/10/00-cover.Du35XCGh_ZBjCLW-1.webp)

#AlephAlpha #Kolibri #OpenWeight #BilingualAI #AISovereignty

---

*Source: [Aleph Alpha releases open-weight Kolibri with 1M context](https://www.testingcatalog.com/aleph-alpha-releases-open-weight-kolibri-with-1m-context/)*
