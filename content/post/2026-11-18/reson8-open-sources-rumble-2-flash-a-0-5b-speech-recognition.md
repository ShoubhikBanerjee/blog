---
title: "Reson8 Open Sources Rumble-2-Flash: A 0.5B Speech Recognition Model"
slug: "reson8-open-sources-rumble-2-flash-a-0-5b-speech-recognition-model"
description: "Reson8 has open-sourced Rumble-2-Flash, a 0.5B-parameter speech recognition model, under the Apache 2.0 license. Designed for 40+ languages, the model competes with systems 3-60x its size while..."
date: 2026-11-18T22:09:17+05:30
tags: [Reson8, SpeechRecognition, OpenSource, LLM, Qwen3]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Open Source", "Audio AI"]
image: "https://huggingface.co/blog/assets/rumble-2-flash/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Reson8 Open Sources Rumble-2-Flash: A 0.5B Speech Recognition Model

Reson8 has open-sourced Rumble-2-Flash, a 0.5B-parameter speech recognition model, under the Apache 2.0 license. Designed for 40+ languages, the model competes with systems 3-60x its size while offering native support in Hugging Face Transformers and vLLM without requiring custom code.

## 🧩 How it works
Rumble-2-Flash utilizes the Qwen3-ASR architecture to ensure day-0 support. To determine how small a model could become before accuracy degraded, the team distilled Rumble-2, a larger production model, into this smaller version using on-policy distillation.

In this process, the student model does not train on transcripts written by the teacher. Instead, it transcribes the audio itself, and the teacher grades that transcript token by token. At every position, the teacher provides its own probability for the next token, and the student learns to match it. Because the student learns from its own outputs, it receives corrections for the specific mistakes it makes, with feedback on every token rather than a single score per clip.

On-policy distillation typically requires the teacher and student to share a tokenizer, which was not the case here. Choosing Qwen3-ASR meant adopting its vocabulary, so the team introduced GOLD to remove this restriction. GOLD merges tokens where the two tokenizers split text differently, allowing both models to be compared over the same text. Tokens present in both vocabularies are compared directly, while others are compared via their sorted probabilities.

## ⚙️ Key details
- **Languages:** Supports 40+ languages with automatic language detection.
- **Output Control:** Allows numbers as digits or words, management of fillers, verbatim repeats, and forced language settings.
- **Performance:** Processes an hour of audio in about half a second, achieving over 7,000 RTFx on full batches.
- **Benchmarking:** On the Open ASR Leaderboard multilingual track (Chinese, German, French, Italian, Spanish, Portuguese, Hindi, Dutch, and English), it averages a 6.96% error rate.
- **Comparison:** This performance is better than Meta's omniASR-LLM 7B (15x larger) and ahead of Whisper large-v3.
- **English Track:** Averages a 6.6% WER.

On AppTek's call-centre benchmark, which includes 302 hours of helpline calls and 14 English accents, Rumble-2-Flash reaches 7.86% WER. This result is on par with NVIDIA's Nemotron 3.5 Transcribe (30B) at 7.78% and well ahead of Qwen3-ASR 0.6B (8.7%). It is close to Qwen3-ASR 1.7B (7.4%), the only model in the comparison that performs better.

| Model | Performance Context |
| :--- | :--- |
| Rumble-2-Flash | 7.86% WER on AppTek call-centre benchmark |
| NVIDIA Nemotron 3.5 Transcribe | 7.78% WER (On par with Rumble-2-Flash) |
| Qwen3-ASR 0.6B | 8.7% WER |
| Qwen3-ASR 1.7B | 7.4% WER |

## 🚀 Availability
The model weights are available on the Hub at Reson8/Rumble-2-Flash. If your stack runs Transformers or vLLM, it runs Rumble-2-Flash, with no forked runtime or `trust_remote_code` required.

![figure](https://huggingface.co/datasets/Reson8/public-media/resolve/main/blog/rumble-2-flash/gold.png)

![figure](https://huggingface.co/datasets/Reson8/public-media/resolve/main/blog/rumble-2-flash/size-vs-wer-en.png)

![figure](https://huggingface.co/datasets/Reson8/public-media/resolve/main/blog/rumble-2-flash/apptek.png)

#Reson8 #SpeechRecognition #OpenSource #LLM #Qwen3

---

*Source: [Rumble-2-Flash: an open 0.5B speech model for 40+ languages](https://huggingface.co/blog/rumble-2-flash)*
