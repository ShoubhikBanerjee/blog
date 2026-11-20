---
title: "Solar framework launches open tools for real-time video world models"
slug: "solar-framework-launches-open-tools-for-real-time-video-world-models"
description: "Solar is an open framework for interactive world models that spans open data, scalable training, long-horizon video generation, and real-time deployment. The repository contains code for two primary..."
date: 2026-11-20T18:09:02+05:30
tags: [SolarFramework, VideoGeneration, WorldModels, OpenSource, MiniMaxH3]
categories: ["AI", "Generative AI", "Computer Vision", "Open Source Software", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/140875206?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Solar framework launches open tools for real-time video world models

Solar is an open framework for interactive world models that spans open data, scalable training, long-horizon video generation, and real-time deployment. The repository contains code for two primary components: SolarWM and SolarRenderer.

## 🧩 How it works
The framework is built around two distinct modules that handle different aspects of video generation and rendering:

| Component | Function |
| :--- | :--- |
| SolarWM | Enables real-time interaction, continuous exploration, and diverse generated worlds. |
| SolarRenderer | Performs four-step, structure-conditioned video rendering with bidirectional and block-causal training and inference on MiniMax-H3. |

## ⚙️ Key details
Several specific model releases and optimizations are included in the Solar framework:

*   **SolarWM-H3 Memory**: Improves long-term scene consistency and preserves visual details across revisits. Weights are available for the 33B model.
*   **SolarWM-H3 Realtime**: Enables low-latency interactive video generation from an image and a prompt, featuring real-time camera control.
*   **H3 Streaming VAE Decoder**: Allows for low-latency streaming video decoding that produces frames as latents arrive. It supports both the official MiniMax-H3 VAE and NVIDIA’s distilled StreamRender-H3 decoder.
*   **Training Efficiency**: Training for SolarWM-H3 is speeded up by 1.9–2.1× across Stage0.5, Stage1, and Stage2 with matching training trajectories, attributed to ResearchBoost-Agent.
*   **Data**: The SolarWM dataset and SolarRenderer dataset are hosted on Hugging Face.

## 🚀 Availability
*   **Code**: SolarWM and SolarRenderer code is available in the repository. Real-time deployment for SolarWM and the H3 Streaming VAE Decoder code are located in the `deploy/solar_wm/` directory.
*   **Weights**: Model weights for both SolarWM and SolarRenderer are available on Hugging Face.
*   **Demonstrations**: An online demo for SolarRenderer is available on Hugging Face Spaces.
*   **Documentation**: Specific documentation for SolarWM is found in `docs/solar_wm/` and for SolarRenderer in `docs/solar_renderer/`.

#SolarFramework #VideoGeneration #WorldModels #OpenSource #MiniMax-H3

---

*Source: [Junchao-cs/SolarWM](https://github.com/Junchao-cs/SolarWM)*
