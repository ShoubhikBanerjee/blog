---
title: "Launch of the Open TTS Leaderboard for Objective Text-to-Speech Evaluation"
slug: "launch-of-the-open-tts-leaderboard-for-objective-text-to-speech-evaluation"
description: "The Open TTS Leaderboard has been developed to provide objective metrics for evaluating text-to-speech models, addressing a landscape where only 16 of 92 models on Artificial Analysis are..."
date: 2026-09-30T22:03:54+05:30
tags: [TTS, OpenSource, MachineLearning, TextToSpeech]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Audio Processing"]
image: "https://huggingface.co/blog/assets/open-tts-leaderboard/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Launch of the Open TTS Leaderboard for Objective Text-to-Speech Evaluation

The Open TTS Leaderboard has been developed to provide objective metrics for evaluating text-to-speech models, addressing a landscape where only 16 of 92 models on Artificial Analysis are open-weights as of September 30, 2026.

## 🧩 How it works

The leaderboard utilizes several objective metrics to assess complementary aspects of model performance:

| Metric | Description | Measurement Method |
| :--- | :--- | :--- |
| Intelligibility | Word/character error rate (WER/CER) | Comparison between prompt and transcript using Qwen3 ASR |
| Speed | RTFx and TTFA | Inverse real-time factor (batched offline) and time-to-first-audio (streaming) on H200 GPU and CPU |
| Speaker Similarity | Cosine similarity (SIM) | Comparison between WavLM speaker embeddings of generated audio and reference clips |

## ⚙️ Key details

* **Ranking Methodology**: Models are ranked by macro-average WER on English splits of Seed TTS Eval and CV3 Eval. For character-based languages (Chinese, Japanese, and Korean), CER is reported.
* **Multilingual Support**: While Seed TTS Eval only provides audio for English and Chinese, other languages are scored based on CV3 Eval (zero shot).
* **Streaming Evaluation**: The "Streaming" tab ranks models by TTFA. For streaming models, this is the time until the first audio chunk arrives; for non-streaming models, it is the time until the full utterance is generated. Testing uses 50 English prompts from CV3-Eval with the first 3 runs dropped as warm-up to report the median TTFA.
* **Voice Cloning**: Users can toggle "Voice cloning" to compare supported models. Certain models, including openbmb/VoxCPM2 and bosonai/higgs-tts-3-4b, show improved average WER when a reference audio is provided.

## 🔍 Overview

* **Top English Models**: hexgrad/Kokoro-82M, Supertone/supertonic-3, and fishaudio/s2-pro lead in English WER averaged across the two splits.
* **Strong Multilingual Models**: k2-fsa/OmniVoice, fishaudio/s2-pro, and FunAudioLLM/Fun-CosyVoice3-0.5B-2512.
* **Visualization**: Pareto plots are used to visualize tradeoffs between WER, speaker similarity (SIM), size, and batched inference (RTFx).

## 💡 Why it matters

By transitioning to objective metrics, the time required to evaluate a model is reduced from a couple of weeks (required for collecting votes) to a couple of hours.

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/open-tts-leaderboard/english_table.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/open-tts-leaderboard/english_pareto.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/open-tts-leaderboard/streaming_table.png)

#TTS #OpenSource #MachineLearning #TextToSpeech

---

*Source: [Open TTS Leaderboard: Scalable Evaluation for Multilingual Text-to-Speech and Voice Cloning](https://huggingface.co/blog/open-tts-leaderboard)*
