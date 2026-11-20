---
title: "New borscht Framework Releases 12 Progressive AI Models"
slug: "new-borscht-framework-releases-12-progressive-ai-models"
description: "The SITP.ai repository now hosts the borscht teaching deep learning framework, providing a progression of twelve models from a simple bigram to post‑trained transformers."
date: 2026-11-20T22:08:48+05:30
tags: [AI, DeepLearning, OpenSource, Transformers]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Open Source Software", "Deep Learning"]
image: "https://avatars.githubusercontent.com/u/14998054?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New borscht Framework Releases 12 Progressive AI Models

The SITP.ai repository now hosts the borscht teaching deep learning framework, providing a progression of twelve models from a simple bigram to post‑trained transformers.

## 🔍 Overview
- The repository hosts the https://sitp.ai textbook and the `borscht` teaching deep learning framework.
- It includes a series of models labeled Model 1 through Model 12.

## 🧩 Model Progression
| Model | Type |
|-------|------|
| Model 1 | Bigram |
| Model 2 | Discriminative Perceptron |
| Model 3 | Probabilistic Perceptron |
| Model 4 | Multilayer Peceptron |
| Model 5 | Convolutional Neural Network |
| Model 6 | Recurrent Neural Network |
| Model 7 | Long Short-Term Memory Network |
| Model 8 | Encoder-Decoder Pre-trained Transformers (BERT) |
| Model 9 | Decoder Only Pre-trained Transformers (mingpt) |
| Model 10 | Decoder Only Pre-trained Transformers (nanogpt) |
| Model 11 | Post-trained Transformer (nanochat) |
| Model 12 | Post-trained Transformer (nanoreasoner) |

## ⚙️ Technical Details
- **Setup**: Run `borscht/setup.sh` to install Python and Rust toolchains.
- **File 3B**: From Managed Python to Native Rust – see `pyproject.toml` / `Cargo.toml`.
- **File 3C**: From Rust to RISC‑V – see `kernelscpu.rs`.
- **File 4A**: From Rust to CUDA Rust.
- **File 4B**: Accelerate Tensor on GPU – `python/borscht/tensor_nativegpu.py`, `rust/kernelsgpu.rs`.
- **File 5**: Abstracting Acceleration with `Dispatcher`, `Storage`, `Allocator` – see `borscht/python/borscht/tensor.py`.
- **File 9**: From Volta to Ampere (sm80).
- **File 10**: From Ampere (sm80) to Hopper (sm90).
- **File 11**: Hello Tensor Compiler.
- **File 12**: Hello Inference Engine.

## 📄 Licensing
- The project is licensed under the June 9 Researcher Reciprocity License, adapting the Open RAIL‑S structure.
- The license restricts using the code to train, fine‑tune, distill, generate synthetic data, embed for training, or otherwise improve an AI model or service without researcher reciprocity.
- Contributors and authorized researchers retain rights to generate outputs, evaluate models, benchmark, publish research, and explore ideas on equal terms to ordinary users.

## 🚀 Next Steps
- After Model 12, the authors suggest reading the research blog series **From SITP to SOTA**:
  - FS2S Part 1 (ARCH/OPT): From modded‑nanogpt to dsv3 and k3.
  - FS2S Part 1 (SYS): From Hopper to Blackwell and Rubin.
  - FS2S Part 2 (DISTSYS): From FSDP to MP.


#AI #DeepLearning #OpenSource #Transformers

---

*Source: [4thd1m/asitpofborscht](https://github.com/4thd1m/asitpofborscht)*
