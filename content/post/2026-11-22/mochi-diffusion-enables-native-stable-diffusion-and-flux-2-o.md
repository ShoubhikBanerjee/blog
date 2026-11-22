---
title: "Mochi Diffusion enables native Stable Diffusion and FLUX.2 on Mac"
slug: "mochi-diffusion-enables-native-stable-diffusion-and-flux-2-on-mac"
description: "Mochi Diffusion is a new native macOS application that allows users to run Stable Diffusion and FLUX.2 Klein models locally and completely offline. The app is built with SwiftUI and leverages Apple's..."
date: 2026-11-22T22:08:30+05:30
tags: [MochiDiffusion, StableDiffusion, MacOS, CoreML, FLUX2, ImageGeneration]
categories: ["AI", "Generative AI", "macOS Software", "Image Generation", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/163610650?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Mochi Diffusion enables native Stable Diffusion and FLUX.2 on Mac

Mochi Diffusion is a new native macOS application that allows users to run Stable Diffusion and FLUX.2 Klein models locally and completely offline. The app is built with SwiftUI and leverages Apple's Core ML implementation for Stable Diffusion and the Iris pipeline for FLUX.2 Klein and Z-Image Turbo to achieve maximum performance and speed with reduced memory requirements.

## 🧩 How it works
The application supports multiple model pipelines and compute configurations:
- **Core ML Stable Diffusion**: Uses specially converted models for Apple hardware. These are extremely fast and memory efficient, especially on Apple Silicon Macs with Neural Engine, though each model generates images of a fixed size baked in during conversion.
- **FLUX.2 Klein and Z-Image Turbo**: Run via the Iris pipeline with native Metal GPU acceleration. No conversion is required for FLUX.2 Klein models.
- **Draw Things Server**: Mochi Diffusion can also generate images using models hosted on a Draw Things server.

For Stable Diffusion, users must convert or download Core ML models. The `split_einsum` version is compatible with all compute unit options, including the Neural Engine, while the `original` version is only compatible with the `CPU & GPU` option. Users need to select the correct model version corresponding to their chosen compute option.

## ⚙️ Key details
- **Compute Options**: `CPU & Neural Engine` provides a balance between speed and low memory usage. `CPU & GPU` may be faster on M1 Max, Ultra, and later chips but uses more memory.
- **Model Management**: The model folder is created by default under the user's home directory, customizable in Settings. Users create a new folder with the desired display name and move or extract converted models into it.
- **Compilation Time**: The first use of a model may take up to 2 minutes for the Neural Engine to compile a cached version; subsequent generations are much faster.
- **Input Handling**: FLUX.2 Klein supports up to 4 input images. Due to pipeline constraints, Mochi automatically resizes inputs to fit the attention budget and indicates the new sizes in the UI.
- **Features**: Includes a built-in gallery with import, save, and sync support. Generated images are saved as PNG with embedded generation settings, readable by AUTOMATIC1111-compatible tools and Civitai uploads (viewable in Finder's Get Info window).
- **Capabilities**: Supports generating images based on a starting image or using ControlNet with Stable Diffusion.

## 🚀 Availability
The app is available for macOS. Users can obtain FLUX.2 Klein model components (text_encoder, tokenizer, transformer, and vae) from provided download links or using the `download_model.sh` script.

#MochiDiffusion #StableDiffusion #MacOS #CoreML #FLUX2 #ImageGeneration

---

*Source: [MochiDiffusion/MochiDiffusion](https://github.com/MochiDiffusion/MochiDiffusion)*
