---
title: "BitVLA: 1-bit Vision-Language-Action Models for Robotics"
slug: "bitvla-1-bit-vision-language-action-models-for-robotics"
description: "BitVLA, a 1-bit Vision-Language-Action model for robotics manipulation, has been released. The official inference framework, robot.cpp, is now available, allowing for inference with I2S-quantized..."
date: 2026-11-18T18:09:03+05:30
tags: [BitVLA, Robotics, AI, VisionLanguageAction, InferenceFramework]
categories: ["AI", "Robotics", "Machine Learning", "AI Models", "Computer Vision"]
image: "https://avatars.githubusercontent.com/u/47163302?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# BitVLA: 1-bit Vision-Language-Action Models for Robotics

BitVLA, a 1-bit Vision-Language-Action model for robotics manipulation, has been released. The official inference framework, robot.cpp, is now available, allowing for inference with I2S-quantized GGUF models without a Python or PyTorch runtime. BitVLA is accepted by CoRL 2026, Spotlight, and has achieved impressive performance metrics.

## 🔍 Overview
- BitVLA is a 1-bit Vision-Language-Action model for robotics manipulation.
- It is accepted by CoRL 2026, Spotlight.
- The pre-trained BitVLA model has been released.

## ⚙️ Key details
- BitVLA achieves 96.6% accuracy on various tasks.
- It has a model size of 3.0B parameters and 1.4GB memory usage.
- Inference with two-image LIBERO inputs takes 39 ms per action chunk on RTX 3090, approximately 9.7× faster than PyTorch eager and 5.4× faster than torch.compile.
- On RTX 4090, it takes just 17 ms per action chunk (58.8 Hz).

## 🚀 Availability
- The official inference framework, robot.cpp, is now available.
- BitVLA can be run with I2S-quantized GGUF models without a Python or PyTorch inference runtime.

## 💡 Why it matters
- BitVLA offers a more efficient and faster inference framework for robotics manipulation tasks.
- It has achieved impressive performance metrics, making it a promising model for robotics applications.

#BitVLA #Robotics #AI #VisionLanguageAction #InferenceFramework

---

*Source: [ustcwhy/BitVLA](https://github.com/ustcwhy/BitVLA)*
