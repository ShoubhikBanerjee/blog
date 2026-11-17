---
title: "Speaches provides an OpenAI-compatible API for speech-to-text and text-to-speech"
slug: "speaches-provides-an-openai-compatible-api-for-speech-to-text-and-text-to-speech"
description: "Speaches is an OpenAI API-compatible server that supports streaming transcription, translation, and speech generation."
date: 2026-11-17T18:10:30+05:30
tags: [OpenAI, SpeechRecognition, TextToSpeech, Docker, API]
categories: ["AI", "Natural Language Processing", "APIs & Integrations", "Developer Tools", "Speech Technology"]
image: "https://avatars.githubusercontent.com/u/192631691?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Speaches provides an OpenAI-compatible API for speech-to-text and text-to-speech

Speaches is an OpenAI API-compatible server that supports streaming transcription, translation, and speech generation.

## 🔍 Overview

- The project aims to be the equivalent of Ollama, but specifically for TTS/STT models.
- It is OpenAI API compatible, meaning all tools and SDKs that work with OpenAI's API should work with `speaches`.
- Supports GPU and CPU environments.
- Deployable via Docker Compose or Docker.
- Highly configurable.
- Includes a Realtime API.

## 🧩 How it works

- **Speech-to-Text**: Powered by `faster-whisper`.
- **Text-to-Speech**: Uses `piper` and `Kokoro` models.
- **Streaming**: Transcription is sent via SSE as the audio is transcribed; users do not need to wait for the audio to fully be transcribed before receiving it.
- **Dynamic Model Loading**: Users specify which model to use in the request, and it is loaded automatically. The model is unloaded after a period of inactivity.

## 💡 Why it matters

Speaches enables specific audio-to-text and text-to-audio workflows:

- Generate a spoken audio summary of a body of text (text in, audio out).
- Perform sentiment analysis on a recording (audio in, text out).
- Support async speech-to-speech interactions with a model (audio in, audio out).

#OpenAI #SpeechRecognition #TextToSpeech #Docker #API

---

*Source: [speaches-ai/speaches](https://github.com/speaches-ai/speaches)*
