---
title: "mlx-audio library brings TTS and STS models to Apple Silicon"
slug: "mlx-audio-library-brings-tts-and-sts-models-to-apple-silicon"
description: "Neywa Labs, the company behind Nativ, has released mlx-audio, an open-source library built on Apple's MLX framework. The tool allows developers to run audio models directly on Apple Silicon (M series..."
date: 2026-11-17T12:12:52+05:30
tags: [AppleSilicon, MLX, TextToSpeech, OpenSource, NeywaLabs, AudioAI]
categories: ["AI", "Machine Learning", "Audio Processing", "Apple Ecosystem", "Open Source Tools"]
image: "https://avatars.githubusercontent.com/u/228382334?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# mlx-audio library brings TTS and STS models to Apple Silicon

Neywa Labs, the company behind Nativ, has released mlx-audio, an open-source library built on Apple's MLX framework. The tool allows developers to run audio models directly on Apple Silicon (M series chips), supporting text-to-speech (TTS), speech-to-text (STT), speech-to-speech (STS), and music generation tasks with fast, optimized inference.

## 🧩 Core Capabilities
The library provides a suite of audio processing features:
*   **Model Support:** Multiple architectures for TTS, STT, STS, and music generation.
*   **Multilingual Support:** Language options vary by model, including English, Japanese, Chinese, French, Spanish, Italian, Portuguese, and Hindi.
*   **Voice Customization:** Features for voice cloning and customization.
*   **Control:** Adjustable speech speed control.
*   **Interface:** An interactive web interface with 3D audio visualization.
*   **API:** An OpenAI-compatible REST API.
*   **Quantization:** Support for 3-bit, 4-bit, 6-bit, 8-bit, and more for optimized performance.

## ⚙️ Model Variants
The evidence lists specific model options available within the ecosystem:

| Model Name | Description |
| :--- | :--- |
| Kokoro | Fast, high-quality multilingual TTS (EN, JA, ZH, FR, ES, IT, PT, HI) available in bf16, 8bit, 6bit, and 4bit.
| KittenTTS | Compact models for edge-friendly TTS (EN) in nano, micro, mini, and collection sizes.
| Qwen3-TTS | Custom voice model, e.g., "mlx-community/Qwen3-TTS-12Hz-0.6B-CustomVoice-8bit". |

## 🚀 Installation and Usage
developers can install and interact with the library using the following methods:
*   **Installation:** 
    *   `pip install -U mlx-audio`
    *   `uv tool install --force mlx-audio --prerelease=allow`
    *   For development: `git clone https://github.com/Blaizzy/mlx-audio.git` followed by `pip install -e ".[dev, server]"`
*   **Integration:** Available as a Swift package for iOS and macOS integration.
*   **CLI Generation:** 
    *   Basic command: `mlx_audio.tts.generate --model mlx-community/Qwen3-TTS-12Hz-0.6B-CustomVoice-8bit --text 'Hello, world!' --voice Vivian`
    *   File handling: By default, generation saves numbered files such as `audio_000.wav` and `audio_001.wav`. Use `--join_audio` to save one combined file.
    *   Streaming: When using `--stream`, add `--save` to write the streamed audio to disk.

#AppleSilicon #MLX #TextToSpeech #OpenSource #NeywaLabs #AudioAI

---

*Source: [Neywa-Labs/mlx-audio](https://github.com/Neywa-Labs/mlx-audio)*
