---
title: "Stable Diffusion runs on Android via Snapdragon NPU acceleration"
slug: "stable-diffusion-runs-on-android-via-snapdragon-npu-acceleration"
description: "Run Stable Diffusion on Android devices using Snapdragon NPU acceleration. This project is now open-sourced and completely free, supporting both NPU and CPU/GPU inference paths."
date: 2026-11-22T22:08:30+05:30
tags: [StableDiffusion, Android, Snapdragon, NPU, OpenSource]
categories: ["AI", "Generative AI", "Mobile Computing", "Open Source", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/157940664?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Stable Diffusion runs on Android via Snapdragon NPU acceleration

## 📢 Overview
Run Stable Diffusion on Android devices using Snapdragon NPU acceleration. This project is now open-sourced and completely free, supporting both NPU and CPU/GPU inference paths.

## 🧩 How It Works
Local Dream is built on top of many excellent open-source projects, including:

| Component | Function |
| :--- | :--- |
| Qualcomm QNN SDK | NPU model execution |
| alibaba/MNN | CPU model execution |
| happyyzy/stable-diffusion.cpp | Deep performance optimizations for on-device DiT inference |
| xtensor-stack | Tensor operations & scheduling |
| mlc-ai/tokenizers-cpp | Text tokenization |
| yhirose/cpp-httplib | HTTP server |
| nothings/stb | Image processing |
| facebook/zstd | Model compression |
| nlohmann/json | JSON processing |
| square/okhttp | HTTP client |
| coil-kt/coil | Image loading & processing |
| MoyuruAizawa/Cropify | Image cropping |
| AOSP, Material Design, Jetpack Compose | UI framework |
| CompVis/stable-diffusion | Base model framework |
| xinhtao/Real-ESRGAN | Image upscaling |
| Kim2091/UltraSharpV2 | Image upscaling |
| bhky/opennsfw2 | NSFW content filtering |

## ⚙️ Key Details
- Currently focused on SD1.5 and SDXL models.
- SD2.1 is no longer maintained due to poor quality and limited popularity.
- SD1.5 models are supported on Snapdragon NPUs with Hexagon V68 architecture or newer.
- SDXL models are supported on Snapdragon 8 Gen 3 and newer devices.
- CPU/GPU inference supports SD1.5 and imported SDXL MNN packages.
- Large SDXL models require substantially more memory than SD1.5.

## 💬 Community
- You can join the Local Dream telegram group for discussion or help with testing.

#StableDiffusion #Android #Snapdragon #NPU #OpenSource

---

*Source: [xororz/local-dream](https://github.com/xororz/local-dream)*
