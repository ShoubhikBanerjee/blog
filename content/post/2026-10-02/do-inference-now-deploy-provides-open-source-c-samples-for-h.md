---
title: "Do Inference Now Deploy provides open‑source C++ samples for hardware‑accelerated AI inference"
slug: "do-inference-now-deploy-provides-opensource-c-samples-for-hardwareaccelerated-ai-inference"
description: "Do Inference Now (DIN) Deploy is an open‑source collection of practical C++ samples that bridges the gap from a model checkpoint to a native, hardware‑accelerated application on Windows and Linux."
date: 2026-10-02T06:06:47+05:30
tags: [AIInference, ONNXRuntime, TensorRT, OpenSource]
categories: ["AI", "Machine Learning", "Computer Vision", "Software Development", "AI Infrastructure"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/din-deploy-featured-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Do Inference Now Deploy provides open‑source C++ samples for hardware‑accelerated AI inference

Do Inference Now (DIN) Deploy is an open‑source collection of practical C++ samples that bridges the gap from a model checkpoint to a native, hardware‑accelerated application on Windows and Linux.

## 🔍 Overview
- Combines **ONNX Runtime** with the **NVIDIA TensorRT RTX execution provider** to help developers move from a model checkpoint to a native, hardware‑accelerated application.
- The same ONNX Runtime API can also be accessed through **WinML 2.0**.
- Supports both Windows and Linux platforms, with Arm64 variants.

## 🧩 How it works
- Each DIN Deploy sample starts with a **Python exporter** that downloads a model checkpoint from Hugging Face and converts it into an **ONNX** artifact.
- The application side is a native **C++ CLI** built on **ONNX Runtime (ORT)**.
- This split keeps model conversion separate from deployment logic, allowing developers to take an exported model into a local application **without requiring a model‑specific runtime**.
- Most sample code uses **ONNX Runtime session and tensor APIs** in C++.
- Vendor‑specific code, including CUDA APIs and kernels, appears only in optional accelerated paths.
- Execution providers that support the required ONNX Runtime tensor APIs can run the shared code.
- ORT’s **copy tensor API** keeps data locality manageable without dedicated vendor API usage in shared code.
- For preprocessing and post‑processing, the **FLUX.2** sample uses ONNX Runtime’s **graphics interop capability** (introduced in version 1.25) with **Vulkan** and **DirectX** for sampling.

## ⚙️ Key features
- **CMake presets** for Windows and Linux, including x86‑64 and Arm64 variants. CMake downloads ONNX Runtime and TensorRT RTX by default.
- **DirectX** is available only on Windows.
- **Automatic Speech Recognition (ASR)** support:
  - Offline transcription with **OpenAI Whisper** across model sizes.
  - Streaming pipelines with **NVIDIA Parakeet TDT** and **NVIDIA Nemotron ASR Streaming**.
- **Meta SAM 2.1** samples enable interactive masking for images and video, producing segmentation masks usable for selection, tracking, and other computer‑vision workflows.
- **FLUX.2‑klein‑4B** sample provides prompt‑driven image generation, includes graphics‑API interops with Vulkan and DirectX, and demonstrates post‑training quantization (PTQ) with **NVIDIA Model Optimizer**.
- Quantized ONNX models are **drop‑in replacements** that require no application‑code changes despite hardware‑dependent quantization.
- Samples show how to move audio through a native application and return transcription results while using GPU acceleration where available.

## 🚀 Getting started
1. Clone the DIN Deploy repository.
2. Choose a CMake preset for your target platform (Windows, Linux, x86‑64, Arm64).
3. Configure and build the project; CMake will fetch ONNX Runtime and TensorRT RTX.
4. Run the Python exporter to download a model from Hugging Face and convert it to ONNX.
5. Execute the native C++ CLI with the **TensorRT RTX** execution provider, or copy the sample code into your own application and use the provided pipeline implementations.

## 📊 Performance
- **Table 1** (in the repository) compares GPU and CPU performance for selected DIN Deploy workloads measured on a **DGX Spark** system.
- The results illustrate the speed benefits of using the TensorRT RTX execution provider over CPU‑only execution.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/din-deploy-featured-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/din-deploy-figure-1.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/09/Deploy-High-Performance-AI-Models-in-Windows-Applications-on-NVIDIA-RTX-AI-PCs-copy-660x370-png.webp)

#AIInference #ONNXRuntime #TensorRT #OpenSource

---

*Source: [Build Local AI Apps with C++ and NVIDIA TensorRT RTX Samples | NVIDIA Technical Blog](https://developer.nvidia.com/blog/build-local-ai-apps-with-c-and-nvidia-tensorrt-rtx-samples/)*
