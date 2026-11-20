---
title: "PyTorch torchtune Development Winds Down in 2025 After Adding Llama 4 Support"
slug: "pytorch-torchtune-development-winds-down-in-2025-after-adding-llama-4-support"
description: "Development of the PyTorch library torchtune wound down in 2025. As a library designed for easily authoring, post-training, and experimenting with Large Language Models (LLMs), torchtune supported..."
date: 2026-11-20T12:08:10+05:30
tags: [torchtune, PyTorch, LLMs, Finetuning, Llama4]
categories: ["AI", "Machine Learning", "Deep Learning Libraries", "AI Post Training"]
image: "https://avatars.githubusercontent.com/u/107212512?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# PyTorch torchtune Development Winds Down in 2025 After Adding Llama 4 Support

Development of the PyTorch library torchtune wound down in 2025. As a library designed for easily authoring, post-training, and experimenting with Large Language Models (LLMs), torchtune supported the entire post-training lifecycle.

## 🔍 Overview
Torchtune is built for authoring, post-training, and experimenting with LLMs. Before winding down in 2025, the library provided support for the entire post-training lifecycle, where a successful post-trained model would typically utilize several of its methods.

## ⚙️ Key details
Torchtune supported a variety of powerful training techniques and features:
- **Multi-node training**: Fully available to allow full finetuning on multiple nodes, enabling users to take advantage of larger batch sizes and models.
- **v0.4.0 Release features**: This release included stable support for features such as activation offloading and multimodal QLoRA.
- **Config management**: Users can check for available configs using the following commands:
  - `tune ls lora_finetune_single_device`
  - `tune ls knowledge_distillation_distributed`
  - `tune ls full_dpo_distributed`
  - `tune ls qat_distributed` or `tune ls qat_single_device`

## 🚀 Model availability
The library built up a diverse suite of supported models, including:
- **Llama 4**: Available with full and LoRA finetuning configs.
- **Qwen3**: Added support with dedicated configs.
- **Llama 3.3 70B**: Supported with configs running on Llama 3.3.
- **Gemma2**: Added support.
- **Qwen2.5**: Support added.
- **Llama 3.2**: Supported models include Llama 3.2 11B Vision, Llama 3.2 3B, and Llama 3.2 1B (with text and vision configs).

#torchtune #PyTorch #LLMs #Finetuning #Llama4

---

*Source: [meta-pytorch/torchtune](https://github.com/meta-pytorch/torchtune)*
