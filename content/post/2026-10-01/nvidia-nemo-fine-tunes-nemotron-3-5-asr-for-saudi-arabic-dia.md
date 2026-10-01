---
title: "NVIDIA NeMo fine‑tunes Nemotron 3.5 ASR for Saudi Arabic dialects"
slug: "nvidia-nemo-finetunes-nemotron-3-5-asr-for-saudi-arabic-dialects"
description: "NVIDIA’s Nemotron 3.5 multilingual ASR model can be specialized for under‑represented Saudi Arabic dialects such as Najdi and Hijazi by following a reproducible fine‑tuning workflow built on the NeMo..."
date: 2026-10-01T22:03:23+05:30
tags: [ASR, NeMo, ArabicDialects, NVIDIA]
categories: ["AI", "Machine Learning", "Speech Recognition", "Natural Language Processing", "AI Deployment"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image3-18-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA NeMo fine‑tunes Nemotron 3.5 ASR for Saudi Arabic dialects

NVIDIA’s Nemotron 3.5 multilingual ASR model can be specialized for under‑represented Saudi Arabic dialects such as Najdi and Hijazi by following a reproducible fine‑tuning workflow built on the NeMo framework.

## 🔍 Overview
- Automatic speech recognition must handle how people actually speak, not only the dominant languages and styles in pre‑training data.
- Regional dialects and local recording conditions are often under‑represented; a multilingual model that scores well on broad benchmarks may still fall short in deployment.
- Saudi Arabic illustrates the gap: a model may recognize Modern Standard Arabic or English yet struggle with Najdi and Hijazi speech or local recording conditions.

## 🛠️ Adaptation recipe
1. **Select target dialects** – the experiment (SADA) focused on Najdi and Hijazi.
2. **Curate a low‑resource corpus** – remove references the model cannot learn and clips that are probably misaligned. Minimal curation retains usable speech while discarding unusable labels and obvious alignment failures.
3. **Apply quality filters** – use NVIDIA NeMo Curator stages:
   - `MonoConversionStage` converts audio to mono.
   - `UTMOSFilterStage` and `SIGMOSFilterStage` score perceived quality and background noise.
   - Instead of default thresholds, run in score‑only mode, inspect distributions, then set corpus‑specific cut‑offs: UTMOS ≥ 1.25, SIGMOS noise ≥ 1.5, SIGMOS overall ≥ 1.5.
4. **Build a weighted replay mix** – interleave a small amount of previously learned data to reduce catastrophic forgetting.
5. **Fine‑tune** –
   - Use partial encoder unfreezing to limit the number of changed parameters (cheaper and faster than a full fine‑tune, with some accuracy trade‑off).
   - Apply length bucketing to reduce padding and make training practical for streaming encoders.
   - Train on two NVIDIA RTX PRO 6000 Blackwell Workstation Edition GPUs for 12,000 steps (baseline experiment).
6. **Evaluate** – test transcription quality on an independent set; offline accuracy can be boosted with beam search and a larger attention context, at the cost of latency and compute.

## 📊 Results
- After curation, **103,559 of 125,490 utterances** were kept, representing **133.7 hours** (82.5 % of the starting set).
- A default UTMOS threshold of 3.0 would have rejected almost everything; the corpus‑specific cut‑offs preserved challenging but usable dialect speech that a generic threshold would have discarded.
- Replay mixing protects only the data it represents; partial unfreezing may need re‑tuning when the mix changes.
- The workflow does **not** generalize to every Arabic dialect or deployment environment.

| Item                     | Value                                                            |
|--------------------------|------------------------------------------------------------------|
| GPUs used                | 2 × NVIDIA RTX PRO 6000 Blackwell Workstation Edition            |
| Retained utterances      | 103,559 / 125,490 (82.5 %)                                        |
| Retained duration        | 133.7 h                                                          |
| UTMOS cutoff             | ≥ 1.25                                                          |
| SIGMOS noise cutoff      | ≥ 1.5                                                            |
| SIGMOS overall cutoff    | ≥ 1.5                                                            |

## ⚙️ Technical choices (not universal defaults)
- **Minimal curation** – removes unusable labels without discarding scarce, difficult speech.
- **Replay mixing** – interleaves a small amount of prior data to mitigate catastrophic forgetting.
- **Partial encoder unfreezing** – limits parameter updates for faster, cheaper fine‑tuning.
- **Length bucketing** – reduces padding for streaming encoders.
- **Beam search / larger attention context** – can improve offline accuracy without retraining, but adds latency and compute.

## 🚀 Availability
- Nemotron 3.5 ASR supports multilingual streaming transcription across **40 language‑locales**, including transcription‑ready Arabic.
- Deployment‑specific dialects and recording conditions still benefit from the fine‑tuning workflow described above.

## 💡 Why it matters
Adapting a high‑capacity multilingual ASR model to local dialects improves transcription quality for speakers whose speech patterns are under‑represented in pre‑training data, while still retaining the model’s ability to handle other languages.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2024/03/asr-nemo-canary-featured-960x540.jpg)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2023/06/speech-ai-summit-graphic-1.png)

#ASR #NeMo #ArabicDialects #NVIDIA

---

*Source: [Fine-Tuning NVIDIA Nemotron for Saudi Arabic Dialects, with a Path to Other Languages | NVIDIA Technical Blog](https://developer.nvidia.com/blog/fine-tuning-nvidia-nemotron-for-saudi-arabic-dialects-with-a-path-to-other-languages/)*
*Source: [Towards Model as a Library: Offline, Community-Sourced AI for Low-Resource African Languages](https://arxiv.org/abs/2609.38574v1)*
