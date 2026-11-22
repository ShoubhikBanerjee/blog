---
title: "WhisperLiveKit: Self-Hosted, Real-Time Speech-to-Text Pipeline"
slug: "whisperlivekit-self-hosted-real-time-speech-to-text-pipeline"
description: "WhisperLiveKit is a self-hosted, ultra-low-latency speech-to-text pipeline that provides real-time transcription, speaker diarization, and translation. It is designed to handle streaming audio..."
date: 2026-11-22T12:09:58+05:30
tags: [WhisperLiveKit, SpeechToText, RealTimeAI, SelfHosted, Translation]
categories: ["AI", "Speech Recognition", "Natural Language Processing", "Software Development", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/38427957?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# WhisperLiveKit: Self-Hosted, Real-Time Speech-to-Text Pipeline

WhisperLiveKit is a self-hosted, ultra-low-latency speech-to-text pipeline that provides real-time transcription, speaker diarization, and translation. It is designed to handle streaming audio efficiently while offering API compatibility with major platforms.

## 🔍 Overview
The system supports real-time, local speech-to-text with streaming Automatic Speech Recognition (ASR), speaker diarization, and translation. It is built to process audio as it is being spoken rather than waiting for complete utterances.

## 🧩 How it works
WhisperLiveKit utilizes state-of-the-art simultaneous speech research for intelligent buffering and incremental processing. Simple Whisper models are not ideal for this use case because they are designed for complete utterances; processing small segments loses context and cuts off words mid-syllable, resulting in poor transcription.

The pipeline integrates several advanced components:
*   **Simul-Whisper/Streaming**: SOTA 2025 ultra-low latency transcription using the AlignAtt policy.
*   **WhisperStreaming**: Low latency transcription using the LocalAgreement policy (SOTA 2023).
*   **Streaming Sortformer**: Advanced real-time speaker diarization (SOTA 2025).
*   **NLLW**: Simultaneous translation from and to 200 languages based on distilled NLLB models.
*   **Qwen3-ASR-causal**: Causal streaming audio encoder where each audio block is encoded exactly once with constant compute per audio second.
*   **AlignAtt4LLM**: Simultaneous translation with decoder-only LLMs featuring attention-gated commits and append-only output.

## ⚙️ Key details
*   **Architecture**: The backend supports multiple concurrent users and includes Voice Activity Detection to reduce overhead when no voice is detected.
*   **APIs**: Provides OpenAI-compatible REST APIs and Deepgram-compatible WebSocket interfaces.
*   **Streaming**: Native WebSocket support is available for real-time streaming.
*   **Language Support**: Check the specific tokenizer documentation for the list of all available languages.
*   **Troubleshooting**: A troubleshooting guide is available for step-by-step fixes collected from recent GPU issues.

## 🚀 Availability
WhisperLiveKit is available for installation and local execution via command-line tools.

*   **Installation**: `pip install whisperlivekit`
*   **Server Execution**: 
    *   `wlk --model base --language en` (Starts server at http://localhost:8000)
    *   `wlk run whisper:tiny` (Auto-pulls model and starts server)
*   **File Transcription**: 
    *   `wlk transcribe meeting.wav`
    *   `wlk transcribe --format srt podcast.mp3 -o podcast.srt` (Generates subtitles)
*   **Model Management**: 
    *   `wlk models` (View installed models)
    *   `wlk pull large-v3` (Download a model)
    *   `wlk rm large-v3` (Delete a model)
*   **Benchmarking**: `wlk bench` (Test speed and accuracy)
*   **API Access**: 
    *   REST: `curl http://localhost:8000/v1/audio/transcriptions -F file=@audio.wav`
    *   SDK: Compatible with OpenAI Python SDK (`client = OpenAI(base_url="http://localhost:8000/v1", api_key="unused")`)
    *   WebSocket: `ws://localhost:8000/asr`

#WhisperLiveKit #SpeechToText #RealTimeAI #SelfHosted #Translation

---

*Source: [QuentinFuxa/WhisperLiveKit](https://github.com/QuentinFuxa/WhisperLiveKit)*
