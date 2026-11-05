---
title: "Phonon: Open‑source On‑device Text‑to‑Speech Model Released"
slug: "phonon-opensource-ondevice-texttospeech-model-released"
description: "Two weeks ago, we opened up Phonon, our small text‑to‑speech model that runs on your own device."
date: 2026-11-05T18:02:42+05:30
tags: [TextToSpeech, OnDeviceAI, OpenSource, EdgeComputing]
categories: ["AI", "Machine Learning", "Speech Synthesis", "Open Source Software", "Edge Computing"]
image: "https://huggingface.co/blog/assets/phonon-closer-look/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Phonon: Open‑source On‑device Text‑to‑Speech Model Released

Two weeks ago, we opened up Phonon, our small text‑to‑speech model that runs on your own device.

## 🔍 Overview
- Phonon runs on your own device, needs no server or network, and your typed text stays with you.
- It works on phones, laptops, single‑board computers and in a browser tab.
- The model was downloaded more than 200,000 times in its first two weeks and is still trending on Hugging Face.

## 🧩 How it works
- Based on the Pocket TTS lineage and uses flow matching to generate audio, a technique different from other TTS systems.
- Generates audio latents autoregressively: each step outputs a latent that becomes the next input, with training loss computed on them.
- Training was initially numerically unstable and required several tricks to achieve quality across five languages.

## ⚙️ Key details
- Two model sizes: about 65 MB and 75 MB.
- Model variants:

| Model | Approx. Size | License | Language Coverage |
|-------|-------------|---------|-------------------|
| Phonon 31m | 65 MB | Apache 2.0 (free for commercial use) | English |
| Phonon 40m | 75 MB | CC BY‑NC (non‑commercial) | English, French, German, Spanish, Portuguese |

- Together the models support English, French, German, Spanish and Portuguese.
- More than 100 built‑in voices; additional voices can be created in Gradium Studio.
- Handles phone numbers, dates and codes, which many TTS systems struggle with.

## 🚀 Performance
- On intelligibility tests, Phonon ranks first in German and Spanish and is in the top three for every evaluated language, alongside models up to 100 × its size.
- It tops the CPU streaming benchmark on time‑to‑first audio, highlighting its speed.
- A new inference framework, ptts, was built for Phonon and supports more than 10 backends (CPU Intel/Arm/WebAssembly, GPU CUDA/Vulkan/Metal/WebGPU, NPU Apple Core ML/Snapdragon®).

## 📦 Availability
- Phonon is included in 🤗 Transformers from version 5.21 as the reference PyTorch implementation.
- The 31 m model (English, Apache 2.0) can be used freely in commercial products.
- The 40 m model (five languages, CC BY‑NC) is free for non‑commercial projects; commercial use follows a pricing model based on number of users, not amount of generated speech.
- Example use cases: on an Apple Watch with Wi‑Fi off, Phonon guides a coffee brew step‑by‑step; on an iPhone with no signal, it counts repetitions during a workout.

![figure](https://huggingface.co/datasets/olesiagradium/video/resolve/main/phonon-ttfa-chart.png)

![figure](https://huggingface.co/blog/assets/open-tts-leaderboard/thumbnail.png)

#TextToSpeech #OnDeviceAI #OpenSource #EdgeComputing

---

*Source: [A Closer Look at Phonon TTS. Launching High-Quality On-Device Speech That Tops the Benchmarks.](https://huggingface.co/blog/phonon-tts)*
