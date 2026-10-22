---
title: "Training Qwen3 on a Single AWS Trainium2 Instance with TorchNeuron and NKI MoE"
slug: "training-qwen3-on-a-single-aws-trainium2-instance-with-torchneuron-and-nki-moe"
description: "This post demonstrates three ways to train the Qwen‑3 model on a single AWS trn2.48xlarge instance equipped with Trainium2 accelerators, using TorchNeuron, torchtitan‑neuron and optional NKI..."
date: 2026-10-22T06:10:45+05:30
tags: [Trainium, TorchNeuron, Qwen3, MoE, Neuron]
categories: ["AI", "Machine Learning", "Deep Learning", "Hardware Acceleration", "Natural Language Processing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-22120-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Training Qwen3 on a Single AWS Trainium2 Instance with TorchNeuron and NKI MoE

This post demonstrates three ways to train the Qwen‑3 model on a single AWS trn2.48xlarge instance equipped with Trainium2 accelerators, using TorchNeuron, torchtitan‑neuron and optional NKI mixture‑of‑experts kernels.

## 🔍 Overview
- TorchNeuron registers Trainium as a native PyTorch device, enabling torchtitan to use it through standard PyTorch interfaces.
- When `torch_neuronx` is installed, TorchNeuron registers the Trainium device and torchtitan detects it at startup.
- The walkthrough runs on a single **trn2.48xlarge** instance (16 Trainium2 accelerators, 128 physical NeuronCores, 64 logical NeuronCores at LNC=2).

## ⚙️ Environment
| Component | Version |
|-----------|---------|
| torch | 2.14.0 |
| torch_neuronx | 2.14.3 |
| transformers | 5.16.0 |
| torchtitan‑neuron | release‑2.33 (0.2.2+neuron.1) |
| Instance | trn2.48xlarge (16 Trainium2, 128 physical NeuronCores, 64 logical NeuronCores) |

## 🚀 Training Configurations
### 1️⃣ Transformers v5 backend
- Uses `AutoModelForCausalLM` to load Hub models and reads/writes published **safetensors**.
- Launches **64 training processes**, one per logical NeuronCore.
- Data‑parallel sharding across all 64 ranks.
- Saves final checkpoint as Hugging Face safetensors.
- Example result for `Qwen/Qwen3-4B-Instruct-2507`:
  - Step‑1 loss **6.54** from published weights.
  - Step‑1 loss **12.43** from random initialization.

### 2️⃣ torchtitan native Qwen3Model
- Switches to torchtitan’s native implementation by changing `config.model_spec`.
- `model_registry("4B", attn_backend="sdpa")` selects the native Qwen3 model with **scaled dot‑product attention (SDPA)**.

### 3️⃣ NKI Mixture‑of‑Experts (MoE) kernels
- Adds Neuron Kernel Interface (NKI) MoE kernels from the `torchtitan‑neuron` recipes.
- Uses torchtitan’s override registry to attach the custom kernel.
- `qwen3_nki_moe_config()` replaces the MoE block with the NKI grouped‑experts implementation, selects SDPA and a gather‑free rotary embedding.
- Configuration details:
  - Data‑parallel sharding across 64 ranks, tensor‑parallel degree **1**.
  - `num_experts=64` sets the number of experts (not the expert‑parallel degree).
  - `CompileConfig(enable=False)` runs the example in **eager mode**.
- TorchNeuron supports the registered NKI operators in both **eager execution** and **`torch.compile`** modes.

## 🧩 Execution Modes
- **Eager mode**: Neuron compiles operations as they execute.
- **`torch.compile`**: Neuron compiles the captured graph.

## 📚 Getting Started
- Use a single `trn2.48xlarge` with either the **AWS Deep Learning AMI for Neuron** or a **Neuron PyTorch training container**.
- Install `torch_neuronx` to enable device registration and torchtitan detection.

## 💡 Why it Matters
- Demonstrates that a single Trainium2‑powered instance can train a 4‑billion‑parameter LLM using standard PyTorch interfaces.
- Shows flexibility: the same hardware can run a Hugging Face Transformers backend, a native torchtitan implementation, or custom NKI MoE kernels without changing the underlying instance.
- Provides a reproducible recipe for researchers and engineers to explore performance trade‑offs between eager execution, graph compilation, and custom kernel extensions.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-22120-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-22120-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-22120-3.jpg)

#Trainium #TorchNeuron #Qwen3 #MoE #Neuron

---

*Source: [Train Qwen3 on AWS Trainium with torchtitan | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/train-qwen3-on-aws-trainium-with-torchtitan/)*
