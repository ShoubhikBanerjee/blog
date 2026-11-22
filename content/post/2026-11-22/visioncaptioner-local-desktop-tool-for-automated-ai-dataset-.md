---
title: "VisionCaptioner: Local Desktop Tool for Automated AI Dataset Captioning"
slug: "visioncaptioner-local-desktop-tool-for-automated-ai-dataset-captioning"
description: "VisionCaptioner is a new local desktop application designed to automate the creation of detailed captions for image and video datasets. Built specifically for AI researchers and enthusiasts training..."
date: 2026-11-22T22:08:30+05:30
tags: [ComputerVision, DatasetCreation, LocalAI, ImageCaptioning, VideoAnalysis]
categories: ["AI", "Computer Vision", "Machine Learning Tools", "Data Processing"]
image: "https://avatars.githubusercontent.com/u/719004?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# VisionCaptioner: Local Desktop Tool for Automated AI Dataset Captioning

VisionCaptioner is a new local desktop application designed to automate the creation of detailed captions for image and video datasets. Built specifically for AI researchers and enthusiasts training custom models, the tool runs entirely on the user's machine to ensure privacy and control.

## 🔍 Overview
The application is aimed at users working with models such as LoRA, Fine-tuning, Flux, Z-Image Turbo, Qwen-Image, SDXL, Wan, and HunyuanVideo. It provides a user-friendly graphical interface (GUI) to manage captioning tasks, along with a command-line interface for scripting options.

## 🧩 How it works
VisionCaptioner leverages Vision-Language Models from the Qwen-VL and Google Gemma 4 families to generate high-quality, context-aware descriptions in batch.

- **Caption Generation**: Automatically generates captions using Qwen-VL or Google Gemma 4 models.
- **Video Support**: Analyzes video files by extracting multiple frames to understand motion and context, a feature distinct from many other tools.
- **LoRA Features**: Includes specific tools for training, such as Trigger Word injection and skipping existing caption files.
- **Editing & Management**: Allows users to quickly review and manually edit captions, and uses find-and-replace functionality with presets to manage the dataset.
- **System Prompts**: Users can choose from built-in presets tuned for various models or write custom instructions.
- **Resolution & Quantization**: Adjustable settings allow users to balance speed, VRAM usage, and descriptive detail.

## 🎨 Masking and Quality Assurance
Beyond standard captioning, the tool supports advanced masking and quality checks for dataset preparation.

| Feature | Description |
| :--- | :--- |
| Masking Support | Creates mask files using the Segment Anything 3 model with promptable subject functionality. |
| Mask Editing | Quick visual editor to paint, edit, extract, or contract masks. |
| Mask Formats | Saves masks as separate files or embedded in image files. |
| Video Extraction | Extracts frames from videos containing a prompted subject. |
| Quality Assurance | Analyzes images for blur, resolution, face/eyes detection, and missing masks. |
| Scoring & Batch | Weighted quality scoring with a sortable table view and batch actions for images below a quality threshold. |

## ⚙️ Key Details and Compatibility
The application supports a wide range of model variants and hardware configurations.

- **Supported Models**: Qwen2.5-VL, Qwen3-VL, Google Gemma 4 (E2B/E4B/26B-A4B/31B), base models, Abliterated versions, and GGUF models (Qwen only for now).
- **OneTrainer Compatibility**: Works with the OneTrainer framework.
- **Hardware Requirements**: 
  - Python 3.10+ 
  - NVIDIA GPU with CUDA 
  - AMD GPU with ROCm on Linux 
  - Apple Silicon Mac (M-series) with Metal / MPS 
- **Quantization Notes**: 
  - FP8 quantization is off by default and requires an NVIDIA GPU with compute capability 8.9+ (RTX 4090 or newer) plus the `kernels<0.15` package.
  - NVIDIA/CUDA-only packages (bitsandbytes, nvidia-ml-py, triton) are skipped automatically on macOS, making Int8/NF4 quantization options unavailable on that platform.

#ComputerVision #DatasetCreation #LocalAI #ImageCaptioning #VideoAnalysis

---

*Source: [Brekel/VisionCaptioner](https://github.com/Brekel/VisionCaptioner)*
