---
title: "Multimodal Generative Framework for Culturally Faithful Ulos Motif Generation"
slug: "multimodal-generative-framework-for-culturally-faithful-ulos-motif-generation"
description: "Researchers have proposed a multimodal generative framework designed to enable the controllable and culturally faithful generation of Ulos motifs."
date: 2026-09-17T22:02:13+05:30
tags: [GenerativeAI, CulturalHeritage, StableDiffusion, LLaMA]
categories: ["AI", "Machine Learning", "Computer Vision", "Digital Preservation"]
author: "Shoubhik Banerjee"
draft: false
---

# Multimodal Generative Framework for Culturally Faithful Ulos Motif Generation

Researchers have proposed a multimodal generative framework designed to enable the controllable and culturally faithful generation of Ulos motifs.

## 🧩 How it works
The framework integrates two primary models:
* **Stable Diffusion XL v1.0**: A Latent Diffusion Model fine-tuned via LoRA.
* **LLaMA 1.5-7B**: A Multimodal Large Language Model.

To guide the generation process, the system employs four complementary conditioning mechanisms:

| Mechanism | Function |
| :--- | :--- |
| Text | Governs semantic intent |
| Image | Governs generation aspects |
| Representation | Governs generation aspects |
| Semantic Map (via ControlNet) | Governs spatial layout |

## ⚙️ Key details
An ablation study conducted across three scenarios—shape transformation, colour variation, and high-complexity input—found that conditioning effectiveness is not proportional to the number of mechanisms combined:

* **Text + Image + Semantic Map**: Achieved the best FID (270) and CLIP Score (0.65 - 0.70), but the weakest SSIM (0.65).
* **Text + Image + Representation**: Offered the best overall balance with a stable SSIM (0.84) and competitive FID (280).
* **All four mechanisms**: Yielded the weakest FID (330), suggesting conflicting optimization signals.

## 💡 Why it matters
Qualitative evaluation showed statistically significant positive acceptance from nine weavers (Wilcoxon, p=0.007) and thirty public participants (p<0.001). Additionally, a web-based prototype supporting image-to-image and text-to-image generation was developed as a digital design tool for cultural heritage preservation.

#GenerativeAI #CulturalHeritage #StableDiffusion #LLaMA

---

*Source: [Multimodal Conditioning of Fine-Tuned Stable Diffusion XL for Controllable and Culturally Faithful Ulos Motif Generation](https://arxiv.org/abs/2609.17987v1)*
