---
title: "PTC-Bias Framework Reduces Word Error Rates in SpeechLLM Decoding"
slug: "ptc-bias-framework-reduces-word-error-rates-in-speechllm-decoding"
description: "Researchers have proposed PTC-Bias, a two-stage framework based on phoneme-level temporal competition designed to improve SpeechLLM decoding performance."
date: 2026-09-25T12:04:19+05:30
tags: [SpeechLLM, ASR, PTCBias, MachineLearning]
categories: ["AI", "Machine Learning", "Speech Recognition", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# PTC-Bias Framework Reduces Word Error Rates in SpeechLLM Decoding

Researchers have proposed PTC-Bias, a two-stage framework based on phoneme-level temporal competition designed to improve SpeechLLM decoding performance.

## 🧩 How it works
PTC-Bias operates through two distinct stages:

* **PTC Retrieval:** Occurs at the prefill stage, performing frame-synchronous phoneme decoding and temporal competition among candidate pronunciations to produce speech intervals and a compact bias-word shortlist.
* **PTC Correction:** Occurs after SpeechLLM decoding, conducting a second local competition between retrieved candidates and mismatched transcript spans within the identified intervals.

## ⚙️ Key details
* **Efficiency:** Both stages use the same phoneme posteriors and do not require an additional SpeechLLM forward pass.
* **Functionality:** Selective correction preserves correct transcriptions while reducing word-segmentation and near-homophone errors.
* **Scalability:** Experiments on LibriSpeech demonstrated consistent gains across two SpeechLLMs with bias lists containing up to 2000 words.

## 💡 Why it matters
When using Prompt-SLAM-ASR-7B with 2000 bias words, PTC-Bias achieved the following relative to CTC-Filter:

| Metric | test-clean | test-other |
| :--- | :--- | :--- |
| B-WER Reduction | 23.4% | 23.9% |
| U-WER | Nearly unchanged | Nearly unchanged |

#SpeechLLM #ASR #PTCBias #MachineLearning

---

*Source: [PTC-Bias: Phoneme-Level Temporal Competition for Bias Retrieval and Post-Decoding Correction in Speech LLMs](https://arxiv.org/abs/2609.28727v1)*
*Source: [Temporal Taxation Compounds Under Post-Training Compression of Whisper Models](https://arxiv.org/abs/2609.28739v1)*
*Source: [BanglaKontho: Closing the Long-Form Gap in Bangla Text-to-Speech](https://arxiv.org/abs/2609.29146v1)*
*Source: [BanglaTurn: A Benchmark and Whisper-Based Model for End-of-Turn Detection in Bangla Speech](https://arxiv.org/abs/2609.29371v1)*
