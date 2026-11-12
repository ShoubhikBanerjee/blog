---
title: "Fine‑tuning TRELLIS.2 3D Model with LoRA Adapters via Hugging Face Jobs"
slug: "finetuning-trellis-2-3d-model-with-lora-adapters-via-hugging-face-jobs"
description: "In this post we release scripts and containers that let you fine‑tune TRELLIS.2, a popular 3D model, on your own 3D assets. The workflow runs locally or on Hugging Face Jobs."
date: 2026-11-12T22:08:51+05:30
tags: [3Dai, LoRA, HuggingFace, FineTuning]
categories: ["AI", "Machine Learning", "3D Modeling", "Computer Vision"]
image: "https://huggingface.co/blog/assets/3d-lora-finetuning/thumbnail.gif"
author: "Shoubhik Banerjee"
draft: false
---

# Fine‑tuning TRELLIS.2 3D Model with LoRA Adapters via Hugging Face Jobs

In this post we release scripts and containers that let you fine‑tune TRELLIS.2, a popular 3D model, on your own 3D assets. The workflow runs locally or on Hugging Face Jobs.

## 🔍 Overview
- TRELLIS.2 improves the representation of 3D structure over its predecessor.
- Fine‑tuning uses LoRA (low‑rank adaptation) adapters added with Hugging Face’s PEFT library.
- The provided scripts require only a few arguments once your dataset is uploaded to the Hugging Face Hub.
- The pipeline can be executed locally or as a containerized job on Hugging Face Jobs.
- 3D generation supports formats such as GLB and PLY and representations like NeRFs and 3D Gaussian splatting.

## 🧩 How it works
TRELLIS.2 processes an input image through five stages:

| Stage | Component | Role |
|---|---|---|
| Background removal | BiRefNet | Removes the image background |
| Encoding | DINOv3‑L | Converts the image into feature tokens |
| Coarse shape prediction | Sparse‑structure flow DiT (diffusion transformer) | Generates a small latent (16³×8) |
| Occupancy grid generation | VAE decoder | Produces a 64×64×64 occupancy grid |
| Detailed geometry | Shape flow DiT + VAE decoder | Generates O‑Voxel geometry at 512×512×512 resolution |
| Material generation | Final decoder | Combines geometry and material into a textured mesh exported as GLB |

LoRA adapters are added to the model that guides the geometry stage and to the DiT that controls shape. No adapters are added to the final material stage.

## ⚙️ Key details
- TRELLIS introduced a unified latent representation; decoders convert it to the required 3D format.
- O‑Voxel is TRELLIS.2’s 3D format; it stores only surface voxels, using ~10% of the grid.
- Converting a mesh to O‑Voxel on a CPU takes seconds; converting back on a GPU also takes seconds.
- Experiments used a subset of GSO with 188 footwear objects; the pretrained model produced correct shoes but often incorrect soles.
- LoRA fine‑tunes by training small adapter matrices while keeping original weights frozen.
- Hugging Face Jobs runs containerized workloads on cloud hardware.

## 🚀 Availability
- Fine‑tuning scripts and Docker containers are provided.
- The workflow accepts a dataset hosted on the Hugging Face Hub.
- Run locally or submit as a Hugging Face Job with minimal argument changes.

## 💡 Why it matters
- 3D generation is used in robotics, simulation, media, and entertainment.
- Fine‑tuning enables creators to adapt a strong base model to specific asset collections.
- The efficient O‑Voxel representation reduces compute waste on empty space.


![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/3d-lora-finetuning/pipeline_lr.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/3d-lora-finetuning/lora_adapters.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/3d-lora-finetuning/stage2_shape.png)

#3Dai #LoRA #HuggingFace #FineTuning

---

*Source: [The Definitive Fine-Tuning Guide for 3D Generation Models](https://huggingface.co/blog/3d-lora-finetuning)*
