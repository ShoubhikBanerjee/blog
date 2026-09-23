---
title: "NVIDIA Releases Nemotron 3 Diarization Open-Weight Model"
slug: "nvidia-releases-nemotron-3-diarization-open-weight-model"
description: "NVIDIA has introduced Nemotron 3 Diarization, an open-weight, 100M-parameter model designed to turn overlapping conversations into speaker-aware data. The model currently ranks #1 on VoiceArena's..."
date: 2026-09-23T22:05:40+05:30
tags: [NVIDIA, Diarization, OpenWeight, SpeechAI, Nemotron]
categories: ["AI", "Machine Learning", "Speech Recognition", "Artificial Intelligence"]
image: "https://cdn-uploads.huggingface.co/production/uploads/688d4bdfdeb55432d90e546d/d_xBvPVTwTB_Rt9yxmp_0.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Nemotron 3 Diarization Open-Weight Model

NVIDIA has introduced Nemotron 3 Diarization, an open-weight, 100M-parameter model designed to turn overlapping conversations into speaker-aware data. The model currently ranks #1 on VoiceArena's Diarization-Bench leaderboard with a 14.72% Diarization Error Rate (DER).

## 🔍 Overview
Nemotron 3 Diarization expands upon earlier models like NVIDIA Streaming Sortformer, which established a four-speaker diarization approach. The new model increases support to eight speakers and improves both throughput and accuracy.

## 🧩 How it works
To process audio, the model must detect speech and assign it to the correct speaker while preserving that assignment through interruptions, silence, or long gaps. The model employs the following technical approach:

* **Arrival-Time Ordering:** Following the Sortformer approach, the model orders output speakers by when they first appear. The first new voice is assigned to the first speaker channel, the second voice to the second channel, and so on. This stabilizes generic speaker labels and removes the need to solve a new speaker permutation for every chunk.
* **Audio Processing:** The model accepts 16 kHz, single-channel audio, converting it into Mel-spectrogram features with a 10 ms frame step. These are stacked by a factor of eight into 80 ms frames for a 31-layer Transformer encoder with rotary positional embeddings (RoPE).
* **Output:** The default output is a [T, 8] floating-point tensor (T time steps by eight speaker channels), where each value represents the probability that a speaker is active. This naturally handles overlap, as multiple channels can be active in the same frame.
* **Context Management:** The Arrival-Order Speaker Cache (AOSC) retains information about speakers from earlier chunks. A first-in, first-out (FIFO) queue provides recent frame context, and the input buffer includes right context (audio immediately after the current chunk).

## ⚙️ Key details

| Feature | Specification |
| :--- | :--- |
| Model Parameters | 100M |
| Max Speaker Support | 8 speakers |
| Input Audio | 16 kHz, single-channel |
| Default Stride | 10 ms (configurable to other multiples of 10 ms) |
| Capabilities | Handles overlapping speech, chunked processing, and customizable streaming latency |

## 💡 Why it matters
Streaming diarization is more difficult than offline processing because a streaming system receives limited context and small chunks of audio rather than the entire recording. 

Regarding speaker identification, the model provides anonymous labels (e.g., speaker_2) rather than real-world identities. Downstream applications can map these IDs to explicit identities using active speaker verification models, user profiles, or meeting metadata.

## 🛠️ Training
The model was trained on public and licensed speech data, including real-world conversations from David AI. This included simulated English and multilingual mixtures spanning 21 languages. The inclusion of David AI data decreased the compound DER from 11.19% to 10.42% at both ultra-low-latency and offline-style operating points.

#NVIDIA #Diarization #OpenWeight #SpeechAI #Nemotron

---

*Source: [**Know Who Spoke When: Build Real-Time, Multi-Speaker AI with NVIDIA Nemotron 3 Diarization**](https://huggingface.co/blog/nvidia/nemotron-diarization)*
