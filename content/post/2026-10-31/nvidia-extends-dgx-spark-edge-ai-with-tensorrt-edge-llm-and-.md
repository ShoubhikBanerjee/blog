---
title: "NVIDIA Extends DGX Spark Edge AI with TensorRT Edge-LLM and Nemotron-3.5 Lightning"
slug: "nvidia-extends-dgx-spark-edge-ai-with-tensorrt-edge-llm-and-nemotron-3-5-lightning"
description: "AI workloads are moving beyond the data center. Developers are building agents that run at the edge—monitoring driver attention, helping robots navigate, and coordinating production‑line fleets...."
date: 2026-10-31T12:02:07+05:30
tags: [NVIDIA, EdgeAI, TensorRT, LLM]
categories: ["AI", "Artificial Intelligence", "Edge Computing", "Machine Learning", "Hardware"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/nvidia-trtedge-chat-terminal-1920x1080-1-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Extends DGX Spark Edge AI with TensorRT Edge-LLM and Nemotron-3.5 Lightning

AI workloads are moving beyond the data center. Developers are building agents that run at the edge—monitoring driver attention, helping robots navigate, and coordinating production‑line fleets. These applications must operate within tight memory, power, and latency budgets. NVIDIA now offers the DGX Spark platform in a 64 GB configuration together with the TensorRT Edge‑LLM runtime, enabling developers to prototype, fine‑tune, and test large‑language models such as Nemotron‑3.5 Lightning directly on edge hardware.

## 🔍 Overview
- Physical AI agents need compact, low‑latency inference.
- DGX Spark 64 GB provides the compute and memory headroom for edge prototyping.
- TensorRT Edge‑LLM delivers a lightweight C++ inference runtime for embedded targets (Jetson Thor, DRIVE AGX Thor, IGX Thor).

## 🧩 How it works
- The `trtedge` command‑line interface (CLI) downloads the selected model (≈21 GB) and builds TensorRT engines optimized for the Spark platform.
- Once built, engines are cached in `~/.cache/tensorrt-edgellm` and reused on later launches.
- A local OpenAI‑compatible API server can host the model, confirming readiness with a `"status":"ready"` JSON response.
- DSpark speculative decoding can be enabled: a draft model proposes several tokens, which the main model validates in a single pass, reducing generation latency.

## ⚙️ Key details
- **Required software stack**: NVIDIA CUDA 13, TensorRT 10.16.1.11 or newer (10.x series), Python 3.10‑3.12.
- **Tested versions**: TensorRT Edge‑LLM 0.11.1 and TensorRT 10.16.1.11.
- Use a Python virtual environment to keep newly installed packages separate while still accessing system‑wide TensorRT libraries.
- Verify the TensorRT version with the provided check command; if bindings are missing, install the compatible TensorRT 10.x package via the NVIDIA TensorRT pip instructions.
- First launch downloads the model and builds the engine; subsequent launches reuse cached engines, accelerating startup.

## 🚀 Performance
- TensorRT Edge‑LLM with Nemotron‑3.5 Lightning yields low response latency and fast token generation on DGX Spark 64 GB.
- DSpark speculative decoding (using three draft tokens) improves generation speed; the exact time‑to‑first‑token (TTFT) and token‑per‑second rates are reported in the reference table.
- Users can tune `num_speculative_tokens` and other settings to balance speed and accuracy for their workload.

## 📦 Availability
- DGX Spark 64 GB configuration is now available for embedded developers.
- TensorRT Edge‑LLM is released with support for the same inference framework on development (Spark) and deployment platforms such as NVIDIA Jetson Thor, NVIDIA DRIVE AGX Thor, and NVIDIA IGX Thor.
- The tutorial demonstrates running the text‑only Nemotron‑3.5 Lightning model on Spark and enabling DSpark speculative decoding.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/03/four-stacked-nvidia-dgx-spark-660x370.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/nvidia-trtedge-chat-terminal-1920x1080-1-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/06/image1-660x370.jpg)

#NVIDIA #EdgeAI #TensorRT #LLM

---

*Source: [Run AI Models for Edge Application Development with Just a Few Commands | NVIDIA Technical Blog](https://developer.nvidia.com/blog/run-ai-models-for-edge-application-development-with-just-a-few-commands/)*
