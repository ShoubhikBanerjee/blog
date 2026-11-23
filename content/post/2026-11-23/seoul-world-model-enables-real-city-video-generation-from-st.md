---
title: "Seoul World Model Enables Real-City Video Generation from Street-View Data"
slug: "seoul-world-model-enables-real-city-video-generation-from-street-view-data"
description: "Researchers have released the Seoul World Model (SWM), a city-scale autoregressive world model that renders videos of the real city of Seoul rather than imagined places. The model fine-tunes a..."
date: 2026-11-23T22:18:20+05:30
tags: [WorldModel, NVIDIA, Seoul, VideoGeneration, RetrievalAugmentedGeneration]
categories: ["AI", "Computer Vision", "Machine Learning", "Generative AI", "Urban Modeling"]
image: "https://avatars.githubusercontent.com/u/73585370?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Seoul World Model Enables Real-City Video Generation from Street-View Data

Researchers have released the Seoul World Model (SWM), a city-scale autoregressive world model that renders videos of the real city of Seoul rather than imagined places. The model fine-tunes a pretrained video world model on 440k Seoul street-view images, real-world driving videos, and synthetic urban data. At generation time, given coordinates, camera actions, and a text prompt, it retrieves nearby street-view images from a reference database and conditions on their geometric and appearance cues—a retrieval-augmented (RAG) recipe that renders faithful videos spanning kilometers of real cityscape. The checkpoint and sample data are provided for non-commercial use under CC BY-NC 4.0, and the checkpoint is a derivative of NVIDIA Cosmos-Predict2.5 subject to the NVIDIA Open Model License. The VAE and text encoder used are publicly available, and every generation runs NVIDIA Cosmos-Guardrail1 for safety checks and face pixelation. Sample data includes everything needed to reproduce the teaser video, though GPU non-determinism means results may differ slightly.

## 🧩 How it works

- Fine-tuned on 440k Seoul street-view images, real driving videos, and synthetic urban data
- Uses a retrieval-augmented approach combining street-view images with geometric and appearance cues
- Takes coordinates, camera actions, and text prompts as input to generate cityscape videos
- Sample data specifies camera paths requiring landscape RGB photos (16:9 or narrower) taken every few meters along a street
- Depth estimation via Depth-Anything-3 provides metric depth and camera poses for each captured image
- Photos must be named to align with a preset trajectory that starts from the first photo by name, covering approximately 45 meters with default settings

## ⚙️ Key details

### Model Components
| Component | Description |
|-----------|-------------|
| Checkpoint | Derivative of NVIDIA Cosmos-Predict2.5, available under CC BY-NC 4.0 and NVIDIA Open Model License |
| VAE | [`Wan-AI/Wan2.1-T2V-1.3B`](https://huggingface.co/Wan-AI/Wan2.1-T2V-1.3B) |
| Text Encoder | [`nvidia/Cosmos-Reason1-7B`](https://huggingface.co/nvidia/Cosmos-Reason1-7B) |
| Guardrail | [`Cosmos-Guardrail1`](https://huggingface.co/nvidia/Cosmos-Guardrail1) used for prompt validation, unsafe content detection, and face pixelation |

### Infrastructure
- All features tested on NVIDIA H100 GPUs
- Generates videos spanning kilometers of real cityscape using retrieval-augmented generation
- GPU non-determinism causes generated results to differ from the original teaser video

## 🚀 Availability

- Repository includes official code for training and generating
- Sample data located in `data/swr_sample/teaser.json` containing camera path, reference images, and prompt used for teaser video
- First run should set `HF_HUB_OFFLINE=0` to allow download via `generate.sh`
- Cosmos-Guardrail1 requires Hugging Face login with accepted license before use
- Depth-Anything-3 installation recommended in separate environment due to numpy version conflicts (SWM requires `numpy>=2`)


#WorldModel #NVIDIA #Seoul #VideoGeneration #RetrievalAugmentedGeneration

---

*Source: [naver-ai/seoul-world-model](https://github.com/naver-ai/seoul-world-model)*
