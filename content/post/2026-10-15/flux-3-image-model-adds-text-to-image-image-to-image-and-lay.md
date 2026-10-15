---
title: "Flux.3 image model adds text‑to‑image, image‑to‑image and layout control"
slug: "flux-3-image-model-adds-texttoimage-imagetoimage-and-layout-control"
description: "Flux.3, the latest model from the FLUX.3 Image Klein collection, is now available for text‑to‑image, multi‑reference image‑to‑image, and bounding‑box layout control."
date: 2026-10-15T22:04:06+05:30
tags: [Flux3, Diffusers, TextToImage]
categories: ["AI", "Machine Learning", "Generative AI", "Computer Vision", "Deep Learning"]
image: "https://huggingface.co/blog/assets/flux3/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Flux.3 image model adds text‑to‑image, image‑to‑image and layout control

Flux.3, the latest model from the FLUX.3 Image Klein collection, is now available for text‑to‑image, multi‑reference image‑to‑image, and bounding‑box layout control.

## 🔍 Overview
- One model for text-to-image, multi-reference image-to-image, and bounding-box layout control.

## 🧩 How it works
- The distilled checkpoint makes a 1024 × 1024 image in about 2 seconds on an H100.
- The distilled checkpoint generates a 1024 × 1024 image in 16 steps by default.
- Pass height, width, or num_inference_steps to change them.
- Pass a reference image (or more) with the image argument.
- Write the prompt as a caption of the image you want, with the change included.
- Add a JSON list of regions after the caption; each region has an id, a bbox, and a desc, and the caption mentions it as <id>.
- Boxes are written as [y_min, x_min, y_max, x_max], y first, on a 0–1000 scale.
- Because the scale is normalized, the same box works at any image size.
- For edits, each region says where its content comes from (src_bbox in the reference) and where it goes (tgt_bbox in the output).

## ⚙️ Key details
- LoRA training scripts for both text-to-image and image editing.
- Ships as a Modular Diffusers pipeline, so you can pop blocks out or add your own.
- Install the latest diffusers and transformers (for the Qwen3-VL text encoder).
- NVFP4 and FP8 weights load with `from_single_file`, for smaller GPUs.
- Both open checkpoints are in the FLUX.3 Image Klein collection.

| Component | Detail |
|---|---|
| Distilled checkpoint | Generates 1024 × 1024 image in about 2 seconds on an H100 |
| Distilled checkpoint (default) | Generates 1024 × 1024 image in 16 steps |
| NVFP4 and FP8 weights | Load with `from_single_file` for smaller GPUs |

## 🚀 Availability
- You can head on to the Hugging Face space and generate some images right now!

## 💡 Why it matters
- FLUX.3 responds best to a full scene description with the subject, the setting, the light, the composition, and the style.
- The official prompting guide from Black Forest Labs has more tips.


![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/flux3/hero.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/flux3/t2i.png)

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/flux3/bbox-layout.png)

#Flux3 #Diffusers #TextToImage

---

*Source: [Welcome FLUX.3 Image Klein in Diffusers](https://huggingface.co/blog/flux-3)*
