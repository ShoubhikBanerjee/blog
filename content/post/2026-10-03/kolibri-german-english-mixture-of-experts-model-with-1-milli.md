---
title: "Kolibri: German-English Mixture‑of‑Experts Model with 1 Million Token Context"
slug: "kolibri-german-english-mixtureofexperts-model-with-1-million-token-context"
description: "On the Day of German Reunification, a new model called Kolibri was released."
date: 2026-10-03T18:03:59+05:30
tags: [Kolibri, MixtureOfExperts, GermanAI, SovereignAI]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Enterprise AI", "AI Governance"]
image: "https://aleph-alpha.com/_astro/00-cover.Du35XCGh_zJqw.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# Kolibri: German-English Mixture‑of‑Experts Model with 1 Million Token Context

On the Day of German Reunification, a new model called Kolibri was released.

## 🔍 Overview
- English‑German Mixture‑of‑Experts Transformer
- 78 B total parameters, 3 B active
- Context length up to 1 M tokens
- Built for sovereign, mission‑critical work in regulated sectors such as public administration, industrials and aerospace
- Specialized for German language, reasoning, math, agentic behavior and other customer‑required capabilities

## 🧩 How it works
- The training pipeline includes data ingestion, curation, ablation experiments, pre‑training, post‑training and final evaluations.
- Hundreds of ablation experiments were run automatically; the pipeline continued without human intervention when hardware failed or a data connection dropped.
- Continuous monitoring of training metrics and standardized monitoring for custom benchmarks were applied.
- A bilingual German/English tokenizer was developed; 21.3 % of pre‑training tokens are German and only 6 % come from translation.
- The model was trained with abstention data and the Merlin‑Arthur protocol, enabling it to respond “I don’t know” when the answer is not present in the context.
- Internal evaluation suites were created for verticals such as the German public sector, aviation, manufacturing and the automotive industry. Synthetic training environments allowed improvement without using customer data.

## ⚙️ Key details
| Model | Total Parameters | Active Parameters | Context Length |
|-------|------------------|-------------------|----------------|
| Kolibri | 78 B | 3 B | 1 M tokens |
| Kolibri Origin | 30 B | 3 B | 65 k tokens |

- The pipeline first validated Kolibri Origin before running Kolibri through the same process.
- Kolibri sits on the Pareto frontier for quality versus serving cost for both English and German; no compared model delivers more quality at the same serving cost, or the same quality at lower cost.
- Across math, coding, grounding and long‑context tasks, Kolibri matches models with up to four times its active parameter count, such as Nemotron 3 Super.

## 🚀 Availability
- Full model weights can be downloaded from Hugging Face.
- The model is released under the Apache 2.0 license.

## 💡 Why it matters
- Full supply‑chain integrity and transparency are provided from data ingestion through final evaluations.
- Customers retain full freedom of deployment and intellectual‑property safety; compliance is an inherited property of the model.
- The small, efficient size allows on‑premise deployment, keeping internal data inside the customer’s environment.
- Specialization yields contextualized performance for specific use cases, and customers can monitor economic impact so that ROI stays measurable and grows over time.
- By optimizing the trade‑off between capability and deployment cost (3 B active out of 78 B total), Kolibri delivers high quality while keeping serving costs low.

![figure](https://aleph-alpha.com/_astro/kolibri-menu.BAr2FBL2_15cIxF.webp)

![figure](https://aleph-alpha.com/_astro/00-cover.Du35XCGh_ZvSBbH.webp)

![figure](https://aleph-alpha.com/_astro/00-cover.C3elmJqh_Z1m2mRc.webp)

#Kolibri #MixtureOfExperts #GermanAI #SovereignAI

---

*Source: [Kolibri Has Landed: A Sovereign Open-Weight Model — Aleph Alpha](https://aleph-alpha.com/en/blog/kolibri-has-landed-a-sovereign-open-weight-model/)*
