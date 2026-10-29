---
title: "AnyLanguageModel adds on‑device speech and decision packages for Swift"
slug: "anylanguagemodel-adds-ondevice-speech-and-decision-packages-for-swift"
description: "Today the AnyLanguageModel project announced two new Swift packages — **AnySpeechRecognizer** and **AnyDecisionModel** — that extend its 1.x Swift API approach to speech transcription and..."
date: 2026-10-29T18:01:40+05:30
tags: [Swift, SpeechRecognition, OnDeviceAI, MachineLearning]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Software Development", "Apple Platforms"]
image: "https://huggingface.co/blog/assets/anydecisionmodel/banner.png"
author: "Shoubhik Banerjee"
draft: false
---

# AnyLanguageModel adds on‑device speech and decision packages for Swift

Today the AnyLanguageModel project announced two new Swift packages — **AnySpeechRecognizer** and **AnyDecisionModel** — that extend its 1.x Swift API approach to speech transcription and decision‑making while keeping a familiar Apple‑style API.

## 🔍 Overview
- **AnySpeechRecognizer** implements Apple’s new SpeechAnalyzer API but lets you pick the underlying engine, including NVIDIA’s Parakeet and Alibaba’s Qwen3‑ASR running locally via Core ML.
- It adds speaker diarization to track who is speaking when.
- **AnyDecisionModel** answers yes‑or‑no, multiple‑choice, and rating‑scale questions, returning typed results and probabilities derived from model logits rather than generated text.
- Both packages can download open models from the Hugging Face Hub and run them entirely on‑device.

## 🗣️ AnySpeechRecognizer
- Mirrors Apple’s SpeechAnalyzer, SpeechTranscriber, DictationTranscriber, SpeechDetector, and AssetInventory components.
- Uses Apple’s Speech framework as the default engine; swapping to a different engine only requires changing the import.
- Supports file‑based and live audio input, volatile results, word timing, and confidence scores when the selected engine provides them.
- Includes built‑in speaker diarization.

## 🤖 AnyDecisionModel
- Provides typed answers (yes/no, multiple‑choice, rating‑scale) with associated probabilities.
- Derives answers from model probabilities, not from text generation.
- Runs on‑device with MLX, Core AI, llama.cpp, or a decision model from Jev or Ollama.
- Can be integrated with the same Swift API style used for language and speech models.

## 📦 Model Options
| Model | Size(s) | Languages / Dialects | Notable Traits |
|-------|--------|-----------------------|----------------|
| Parakeet v3 (NVIDIA) | 0.6 B | 25 European languages (auto‑detect locale) | Runs on Core ML runtime, supports file & live input, volatile results, word timing, confidence |
| Parakeet Ultra (Moondream) | 0.6 B (post‑trained) | Same as v3 | More accurate in most measurements |
| Parakeet Unified (NVIDIA) | – | English only | – |
| Qwen3‑ASR (Alibaba) | 0.6 B, 1.7 B | 30 languages + 22 Chinese dialects (Mandarin, Cantonese, Japanese, Korean) | Provides a single final result per ≤40 s segment, no volatile results, no word timing or confidence, runs on GPU, slower than Parakeet, better for file transcription |

## ⚙️ How it works
- You create a **SpeechAnalyzer** (or **AnySpeechRecognizer**) and attach modules such as **SpeechTranscriber** and **SpeechDetector**.
- Provide an audio file or a stream of audio buffers; results are delivered via asynchronous sequences as they become available.
- **AssetInventory** handles model installation; downloads occur only when the app requests them.
- Models are stored in the standard Hugging Face cache, allowing a macOS app outside the sandbox to share them with Python or other Hugging Face tools.

## 🚀 Availability
- Packages are available as Swift packages; they depend on the 1.x releases of **AnyLanguageModel** and **swift‑huggingface**.
- Approximate download sizes (per model):
  - Parakeet variants: ~600 MB each + ~590 MB for the live encoder.
  - Qwen3‑ASR: 0.9 GB to 2.4 GB depending on model size.
  - Sortformer (used for speaker diarization): ~250 MB.
- Once downloaded, models run entirely on‑device, with no ongoing cloud usage required.


![figure](https://huggingface.co/blog/assets/anylanguagemodel-1-0/banner.png)

![figure](https://huggingface.co/blog/assets/anylanguagemodel/banner.png)

#Swift #SpeechRecognition #OnDeviceAI #MachineLearning

---

*Source: [Introducing AnySpeechRecognizer and AnyDecisionModel: Open Models for Speech and Decisions on Apple Platforms](https://huggingface.co/blog/anydecisionmodel)*
