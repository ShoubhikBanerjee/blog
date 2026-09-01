---
title: "Hugging Face releases WebGPU kernels library and Fleet benchmarking suite"
description: "Hugging Face has released @huggingface/kernels, a minimal library for loading and running optimized WebGPU kernels from the Hugging Face Hub, alongside an initial collection of 207 kernels and Fleet,..."
date: 2026-09-01T22:04:40+05:30
tags: [WebGPU, HuggingFace, GPU, MachineLearning, Kernels, Benchmarking]
categories: [AI]
image: "https://huggingface.co/blog/assets/webgpu-kernels/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Hugging Face releases WebGPU kernels library and Fleet benchmarking suite

Hugging Face has released @huggingface/kernels, a minimal library for loading and running optimized WebGPU kernels from the Hugging Face Hub, alongside an initial collection of 207 kernels and Fleet, an in-browser GPU benchmarking and testing suite.

## 🔍 Overview
- The library enables loading and running WebGPU kernels directly from the Hugging Face Hub.
- The initial collection includes 207 kernels covering operations used across various machine learning architectures and workloads.
- Each kernel is published as a complete, versioned package with its interface, shader templates, correctness cases, benchmark cases, and usage instructions.

## 🧩 How it works
- WebGPU provides a portable API for GPU operations across modern browsers, with WGSL as the shader language.
- Performance and behavior of shaders can vary based on workgroup sizes, memory access patterns, vectorization, data types, fusion strategies, input shape, device, browser, and available WebGPU features.
- @huggingface/kernels bridges kernel repositories and applications: call `getKernel` with a Hub repository ID and contract version, then invoke the returned function with typed input data and tensor shapes.

## ⚙️ Key details
- Each kernel has its own repository and kernel card, documenting semantics, inputs, outputs, attributes, supported data types, source files, and a ready-to-run example.
- The `manifest.json` file defines the operation contract.
- `test.json` contains correctness cases for implementation validation.
- `bench.json` includes benchmark and tuning cases for performance evaluation.
- Kernels can serve as reference implementations for developers building custom WebGPU kernels or integrating operations into their own runtimes.

## 🚀 Availability
- Running kernels requires a browser with WebGPU support, which depends on the browser, operating system, GPU, and driver.
- WebGPU availability can be checked in JavaScript with `"gpu" in navigator`.

## 💡 Why it matters
- Fleet allows users to benchmark and test kernels on their hardware, contributing performance and correctness evidence from real-world devices.
- With user consent, Fleet collects private evidence to identify failures, improve kernel variants, and optimize decisions across diverse hardware.
- The versioned, self-contained kernel packages ensure reproducibility and ease of integration.

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/webgpu-kernels/ai-onnx-add.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/webgpu-kernels/kernels.png)

#WebGPU #HuggingFace #GPU #MachineLearning #Kernels #Benchmarking

---

*Source: [Introducing @huggingface/kernels: 200+ WebGPU Kernels for Local AI](https://huggingface.co/blog/webgpu-kernels)*
