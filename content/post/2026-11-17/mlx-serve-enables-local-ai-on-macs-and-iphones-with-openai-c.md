---
title: "MLX-Serve enables local AI on Macs and iPhones with OpenAI compatibility"
slug: "mlx-serve-enables-local-ai-on-macs-and-iphones-with-openai-compatibility"
description: "MLX-Serve is a native application and local server for macOS that allows users to run open models locally for chat, coding agents, image generation, video, music, speech, and 3D tasks. It speaks the..."
date: 2026-11-17T18:10:30+05:30
tags: [MLXServe, LocalLLM, AppleSilicon, OpenAI, Mac]
categories: ["AI", "Local LLM", "Developer Tools", "Apple Silicon", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/3418467?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# MLX-Serve enables local AI on Macs and iPhones with OpenAI compatibility

MLX-Serve is a native application and local server for macOS that allows users to run open models locally for chat, coding agents, image generation, video, music, speech, and 3D tasks. It speaks the OpenAI, Anthropic, and Ollama APIs, runs offline, requires no Python or account, and is MIT licensed.

## 🚀 Availability

- **macOS**: Requires macOS 26.2 or later on Apple Silicon. It includes a native app and a local server listening on `http://localhost:11234`.
- **iPhone**: An extension called MLX-Serve puts the engine on iPhone, supporting A17 Pro-class devices or newer running iOS 26.
- **Linux**: Release downloads are available for NVIDIA GPUs, supporting x64 for RTX 20 to 50 cards, and arm64 for DGX Spark, GH200, and Jetson Thor.
- **Windows**: A script is provided to build it on Windows systems with NVIDIA cards.
- **Licensing**: The project is MIT licensed.

## 💡 Why it matters

The tool provides a unified local endpoint that supports multiple API standards simultaneously. This allows users to connect existing OpenAI, Anthropic, or Ollama clients to local models without cloud dependencies.

## ⚙️ Key details

### API and Model Support

- Supports OpenAI chat, completions, and Responses; Anthropic Messages; and Ollama APIs.
- Features include streaming, tool calls, JSON schemas, vision, and reasoning.
- Compatible with any MLX model with a supported architecture and any GGUF format.
- Specific models supported include GLM-5.3-Flash and DeepSeek-V4.1-Flash (runnable on a 128 GB Mac by reading experts from the SSD).
- Generative models available in the app or over HTTP include FLUX.2, Qwen-Image, Krea, MOSS-Image, LTX-Video, MiniMax-H3, ACE-Step, YuE2, Qwen3-TTS with voice cloning, and Hunyuan3D.
- Speech-to-text is supported in 30 languages with word timings and speaker identification.

### Performance and Hardware

- **Mac Clustering**: Two Macs connected via a Thunderbolt 5 cable can run one model together; Macs on a network can also use each other's models.
- **Speed Improvements**: On an M4 Max, models decode 10% to 51% faster in v26.11.1 compared to v26.8.
- **Integration**: `mlx-serve launch claude` starts Claude Code against the local Mac, configured with the model's actual context window.
- **Updates**: The application updates itself automatically and suggests models that fit the specific Mac.

## 🔍 Overview

The server provides a built-in web console accessible by opening the local address in a browser. It is designed to run offline, removing the need for cloud accounts or Python environments.

#MLX-Serve #LocalLLM #AppleSilicon #OpenAI #Mac

---

*Source: [hekmon/comfyui-openai-api](https://github.com/hekmon/comfyui-openai-api)*
*Source: [ddalcu/mlx-serve](https://github.com/ddalcu/mlx-serve)*
