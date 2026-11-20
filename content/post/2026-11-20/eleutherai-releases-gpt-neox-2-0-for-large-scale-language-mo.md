---
title: "EleutherAI releases GPT-NeoX 2.0 for large-scale language model training"
slug: "eleutherai-releases-gpt-neox-2-0-for-large-scale-language-model-training"
description: "EleutherAI has announced version 2.0 of the GPT‑NeoX library, a framework for training massive autoregressive language models on GPU clusters. The update moves the codebase onto the latest DeepSpeed..."
date: 2026-11-20T22:08:48+05:30
tags: [GPTNeoX, EleutherAI, DeepSpeed, LargeScaleTraining]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Open Source Software", "High-Performance Computing"]
image: "https://avatars.githubusercontent.com/u/68924597?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# EleutherAI releases GPT-NeoX 2.0 for large-scale language model training

EleutherAI has announced version 2.0 of the GPT‑NeoX library, a framework for training massive autoregressive language models on GPU clusters. The update moves the codebase onto the latest DeepSpeed release and adds versioned releases for backward compatibility.

## 🔍 Overview
- Implementation of model‑parallel autoregressive transformers on GPUs.
- Built on NVIDIA's Megatron Language Model and augmented with DeepSpeed techniques and novel optimizations.
- Repository records EleutherAI's library for training large‑scale language models on GPUs.

## 🧩 How it works
- Employs model parallelism to distribute transformer layers across multiple GPUs.
- Supports launch via Slurm, MPI, and the IBM Job Step Manager.
- Executed at scale on NVIDIA and AMD GPUs on platforms such as AWS, CoreWeave, ORNL Summit, ORNL Frontier, LUMI, and CINECA Leonardo.

## ⚙️ Key details
- Two versioned releases are provided:
  - **Version 2.0** – built on the latest upstream DeepSpeed and maintained going forward.
  - **Version 1.0** – snapshots of the older stack used for GPT‑NeoX‑20B and the Pythia Suite.
- Prior to 3/9/2023, GPT‑NeoX relied on DeeperSpeed, which was based on DeepSpeed 0.3.15.
- Leverages many of the same features as the Megatron‑DeepSpeed library but with increased usability and novel optimizations.
- Not intended for generic inference; for inference‑only needs, Hugging Face `transformers` is recommended.

## 🚀 Availability & Adoption
- More than 40 organizations in academia, industry, and government have used GPT‑NeoX to train over 50 models.
- Notable model families include:
  - Pythia (EleutherAI)
  - StableLM (Stability AI)
  - RedPajama‑INCITE (Together.ai)
  - FORGE (Oak Ridge National Lab)
  - Sarashina1 (SB Intuitions)
  - TildeOpen‑30B (Tilde)
- Evo 2 from the Arc Institute was trained with Savanna, a framework derived from GPT‑NeoX.
- A full list of models and publications is maintained in `USERS.md`.

## 💡 Why it matters
- Provides a centralized, accessible location for techniques that train large‑scale autoregressive language models.
- Accelerates research into large‑scale training by offering a usable, versioned codebase and support for diverse HPC environments.

#GPTNeoX #EleutherAI #DeepSpeed #LargeScaleTraining

---

*Source: [EleutherAI/gpt-neox](https://github.com/EleutherAI/gpt-neox)*
