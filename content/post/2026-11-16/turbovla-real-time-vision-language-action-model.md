---
title: "TurboVLA: Real-Time Vision-Language-Action Model"
slug: "turbovla-real-time-vision-language-action-model"
description: "TurboVLA is a real-time vision-language-action model that achieves 32 Hz on an RTX 4090 with <1 GB VRAM."
date: 2026-11-16T22:14:27+05:30
tags: [AIagents, ComputerVision, MachineLearning]
categories: ["AI", "Machine Learning", "AI Agents", "Computer Vision"]
image: "https://avatars.githubusercontent.com/u/217294675?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# TurboVLA: Real-Time Vision-Language-Action Model

## 🔍 Overview
TurboVLA is a real-time vision-language-action model that achieves 32 Hz on an RTX 4090 with <1 GB VRAM.

## 🧩 How it works
TurboVLA adopts a direct V+L→A mapping instead of using a large language model as the central interface.
It independently encodes visual observations and language instructions, directly exchanging information between them through lightweight bidirectional vision-language interaction.

## ⚙️ Key details
* Achieves an 88.06% average success rate on RoboTwin 2.0.
* Achieves 97.6% average success with only 0.2B parameters, 31.2ms inference latency, and 0.9GiB inference VRAM on a consumer-grade RTX 4090.
* A 0.4B TurboVLA achieves 88.06% success on RoboTwin 2.0, even matching or outperforming substantially larger VLA policies.

## 🚀 Availability
* Clone the repository: git clone https://github.com/H-EmbodVis/TurboVLA.git
* Use Python 3.9.25 for the LIBERO reference environment and Python 3.10 for RoboTwin.
* Install torch==2.3.1 torchvision==0.18.1 --index-url https://download.pytorch.org/whl/cu121 for the LIBERO environment.
* Released the TurboVLA model checkpoints on Hugging Face.
* Released the paper, training and evaluation code.
* Released the LIBERO inference latency benchmark code.

## 💡 Why it matters
TurboVLA achieves high performance without requiring an LLM-centric execution pathway.
It directly constructs task-conditioned representations while avoiding the overhead of an LLM-centric execution pathway.


#AIagents #ComputerVision #MachineLearning

---

*Source: [H-EmbodVis/TurboVLA](https://github.com/H-EmbodVis/TurboVLA)*
