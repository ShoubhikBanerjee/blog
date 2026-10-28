---
title: "NVIDIA Launches RTX Spark Platform with DLSS 5 and Nemotron 3.5 AI Model"
slug: "nvidia-launches-rtx-spark-platform-with-dlss-5-and-nemotron-3-5-ai-model"
description: "NVIDIA introduced RTX Spark, a new Windows PC platform that combines a Blackwell RTX GPU and Grace CPU for AI development, creation, and gaming in slim laptops and compact desktops."
date: 2026-10-28T12:05:05+05:30
tags: [NVIDIA, DLSS5, AIModels, Gaming, RTXSpark]
categories: ["AI", "Hardware", "Graphics Technology", "Artificial Intelligence", "Gaming"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image6-2-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Launches RTX Spark Platform with DLSS 5 and Nemotron 3.5 AI Model

NVIDIA introduced RTX Spark, a new Windows PC platform that combines a Blackwell RTX GPU and Grace CPU for AI development, creation, and gaming in slim laptops and compact desktops.

## 🔧 Platform Details
- Powered by an NVIDIA Blackwell RTX GPU and NVIDIA Grace CPU.
- Supports up to 128 GB of unified memory.
- Runs the full NVIDIA CUDA stack and RTX technologies, including ray tracing and DLSS 5.
- Includes the updated NVIDIA DLSS 4.5 plugin for Unreal Engine 5.8 with official Windows on Arm (WoA) support.
- Native ARM64 binaries allow developers to build and package UE 5.8 applications for RTX Spark systems.

## 🎮 DLSS 5 Features
| Technology | Description |
|------------|-------------|
| Super Resolution | Reconstructs frames from a lower‑resolution input to improve performance. |
| Ray Reconstruction | Generates additional pixels to enhance ray‑traced scenes. |
| Dynamic Multi Frame Generation | Can generate up to five additional frames per rendered frame; the multiplier adjusts automatically to maximize smoothness. |
| 3D‑Guided Neural Rendering | Supported on RTX Spark starting with NBA 2K27. |

- DLSS 5 adds a final stage to the graphics pipeline that enhances lighting and material detail while keeping the engine‑rendered frame as the foundation.
- Avalanche Software used DLSS 5’s SDK controls to preserve artistic intent in their game.
- The latest NVIDIA app beta adds a faster Performance Mode (Preset C) for Frame Generation with minor image‑quality trade‑offs.
- An October model update runs 2× faster than the September version, halves GPU overhead, and reduces VRAM usage at 4K by 20% while keeping comparable visual fidelity.
- The model will ship by default in future DLSS 5 games.

## 🤖 In‑Game AI with Nemotron 3.5
- Nemotron 3.5 Bolt E4B 4 GB is now available.
- Provides ~40 % higher average quality against the prior model on relevant benchmarks.
- Produces up to ~80 % fewer tokens compared with peers.
- Engineered for maximum intelligence and speed per GB of memory, enabling responsive local experiences while preserving headroom for graphics rendering and local speech models.
- Designed to power richer, faster in‑game character interactions with strong conversational capability, autonomous multi‑turn tool use, instruction adherence, and grounding to game state.
- Features a **Conversational mode** toggle for concise, speech‑ready responses.
- **Configurable reasoning** lets developers enable or disable reasoning to meet latency targets.

## 🚀 Performance Improvements
- On supported GeForce RTX 50 Series and RTX PRO Blackwell GPUs, Dynamic Multi Frame Generation adapts the frame‑generation multiplier as workloads change, with a 6× Multi Frame Generation producing up to five additional frames per rendered frame.
- The October model update halves GPU overhead and cuts VRAM use at 4K by 20%.

## 📦 Availability
- RTX Spark ships with the full CUDA stack, DLSS 5 support, and the updated DLSS 4.5 plugin for Unreal Engine 5.8.
- Nemotron 3.5 Bolt E4B 4 GB runs locally on GeForce RTX and RTX Spark devices.
- Early‑access integrations, such as NBA 2K27, already showcase DLSS 5 on RTX Spark.
- Wider rollout to future DLSS 5 titles is planned.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/dlss5_comparison-1.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image6-2-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/image2-1.gif)

#NVIDIA #DLSS5 #AIModels #Gaming #RTXSpark

---

*Source: [NVIDIA RTX Spark Powers Neural Rendering and AI Characters in Games | NVIDIA Technical Blog](https://developer.nvidia.com/blog/nvidia-rtx-spark-powers-neural-rendering-and-ai-characters-in-games/)*
