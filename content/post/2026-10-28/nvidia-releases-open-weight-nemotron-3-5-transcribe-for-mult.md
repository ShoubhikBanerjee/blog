---
title: "NVIDIA Releases Open-Weight Nemotron 3.5 Transcribe for Multilingual Speech Tasks"
slug: "nvidia-releases-open-weight-nemotron-3-5-transcribe-for-multilingual-speech-tasks"
description: "NVIDIA has open‑sourced Nemotron 3.5 Transcribe, a single checkpoint model that handles transcription, speaker attribution, translation, and audio question answering across many languages."
date: 2026-10-28T22:03:50+05:30
tags: [NVIDIA, SpeechAI, OpenSource, Multilingual]
categories: ["AI", "Machine Learning", "Speech Processing", "Open Source AI", "Natural Language Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/68127936de624fb6f57d9989/3vFxCEUXz_xJVrTBr4hNr.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Open-Weight Nemotron 3.5 Transcribe for Multilingual Speech Tasks

NVIDIA has open‑sourced Nemotron 3.5 Transcribe, a single checkpoint model that handles transcription, speaker attribution, translation, and audio question answering across many languages.

## 🔍 Overview
- Open‑weight model available on Hugging Face and ModelScope.
- Leads open‑weight rankings on the Hugging Face Open ASR Leaderboard (English) and on speaker‑attribution benchmarks.
- Supports recordings up to one hour and up to eight simultaneous speakers.

## 🧩 How it Works
- Architecture combines a speech encoder with a hybrid Mamba–Transformer mixture‑of‑experts language model.
- Approximately 30 B total parameters, but only about 4 B are active per token, placing it on Artificial Analysis’s accuracy‑vs‑active‑parameter Pareto frontier.
- Sortformer speaker cues are injected into the language model, enabling turn‑by‑turn speaker tagging during generation.
- Word‑level timestamps are provided for all outputs.

## ⚙️ Key Details
- **Languages**: Transcribes 40 languages, translates 31 languages to or from English, and performs speaker attribution in 13 languages.
- **Benchmark Performance**:
  - English average WER: **5.33 %** (first among open‑weight models, API models excluded).
  - Multilingual mean WER across seven languages: **4.62 %** (lowest among evaluated open‑weight models).
  - Long‑form (up to one hour) mean WER: **10.98 %** (lowest in the Open ASR comparison).
  - Speaker attribution: lowest diarization error on David AI’s 21‑language leaderboard and first place in VoiceArena’s 14‑system comparison.
  - AA‑WWER: **2.80 %** with ~4 B active parameters, tying for first among open‑weight models.
  - On AA‑AgentTalk (voice‑agent set), WER **1.8 %**, better than the next best open‑weight model (2.3 %).
- **Prompt‑Level Control**: Users can guide output with natural‑language instructions, choose processing location, and adapt to domain vocabulary and accents.
- **Fine‑Tuning**: Granary v2 multilingual data and NeMo Speech fine‑tuning tools let developers define target written forms and adapt the model to specific speech domains. In a medical case study, fine‑tuning reduced WER on held‑out speakers by **45.8 %** relative to the best prompt.
- **Use‑Case Examples**:
  - Captioning the 1940 film *His Girl Friday* with speaker labels, including overlapping dialogue.
  - Agora’s classroom demo: word‑level timestamps displayed alongside replay video, letting students see what was said and when.

## 🚀 Availability
- Model checkpoint, Granary v2 data pipeline, and fine‑tuning recipes are publicly hosted on Hugging Face and ModelScope.
- Quantized versions will be released soon, enabling local execution on RTX Spark, DGX Spark, Jetson AGX Thor, or scaling on Blackwell data‑center GPUs.

## 💡 Why It Matters
- Provides a single open‑weight solution for multiple speech‑related tasks, reducing the need for separate models.
- Sets new accuracy benchmarks for open‑weight speech systems while keeping active computational cost low.
- Open data and fine‑tuning recipes empower developers to adapt the model to specialized domains such as medical transcription.
- The upcoming quantized releases lower the barrier for edge deployment and private‑cloud use cases.

#NVIDIA #SpeechAI #OpenSource #Multilingual

---

*Source: [NVIDIA Nemotron 3.5 Transcribe and Granary v2: Intelligent Multilingual Transcription You Can Prompt and Adapt](https://huggingface.co/blog/nvidia/nemotron-transcribe-granary)*
