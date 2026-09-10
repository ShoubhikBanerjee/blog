---
title: "BuzzASR Introduces Fine-Tuned Whisper Models for 102 Languages"
slug: "buzzasr-introduces-fine-tuned-whisper-models-for-102-languages"
description: "Researchers have introduced BuzzASR, a collection of language-specialized fine-tuned Whisper models designed for automatic speech recognition (ASR) across 102 languages."
date: 2026-09-10T22:04:27+05:30
tags: [ASR, Whisper, MachineLearning, OpenSource]
categories: ["AI", "Machine Learning", "Speech Recognition", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# BuzzASR Introduces Fine-Tuned Whisper Models for 102 Languages

Researchers have introduced BuzzASR, a collection of language-specialized fine-tuned Whisper models designed for automatic speech recognition (ASR) across 102 languages.

## 🔍 Overview
BuzzASR scales a simple fine-tuning approach to 102 languages covered in the FLEURS dataset. The development includes a language adaptation strategy that utilizes:
* Monolingual tokenizer replacement
* Data augmentation via text-only fine-tuning

## ⚙️ Key details
BuzzASR demonstrates significant performance improvements over Whisper-large-v3:
* **Language Performance:** Outperforms Whisper-large-v3 on 77 of 102 languages.
* **Error Reduction:** Reduces character error rates (CER) by an average factor of over 2.8.
* **State-of-the-Art Results:** Achieves state-of-the-art CER among open-source systems on 27 of 102 languages when using the combined FLEURS and Common Voice test set.
* **Compression:** The tokenizer replacement strategy provides an average 3.3x improvement in compression rate (characters per token) compared to Whisper's multilingual BPE, with maximum gains reaching 21.7x.

## 🚀 Availability
All models, code, and detailed results have been released.

#ASR #Whisper #MachineLearning #OpenSource

---

*Source: [BuzzASR: A Swarm of 100+ Monolingual Speech Recognition Models](https://arxiv.org/abs/2609.09554v1)*
*Source: [SEA-SpeechBench: A Large-Scale Multitask Benchmark for Speech Understanding Across Southeast Asia](https://arxiv.org/abs/2609.09672v1)*
*Source: [X2-NativeCursor: Native-Token Text Progress Tracking for Incremental-Text Streaming Codec TTS](https://arxiv.org/abs/2609.09677v1)*
*Source: [StreamAlign: Streaming Text-Aligned Speech Tokenization](https://arxiv.org/abs/2609.09719v1)*
*Source: [$S^3$-Bench: Evaluating Speech Interaction Models as Scientific Voice Assistants](https://arxiv.org/abs/2609.09852v1)*
*Source: [Leveraging Fine-grained Error Correction in Korean Speech Recognition for Consultation Services](https://arxiv.org/abs/2609.09889v1)*
