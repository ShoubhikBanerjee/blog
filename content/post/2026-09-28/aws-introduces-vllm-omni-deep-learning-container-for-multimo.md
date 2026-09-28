---
title: "AWS Introduces vLLM-Omni Deep Learning Container for Multimodal Generation"
slug: "aws-introduces-vllm-omni-deep-learning-container-for-multimodal-generation"
description: "AWS has released the vLLM-Omni Deep Learning Container (DLC) for Amazon SageMaker AI, extending vLLM capabilities beyond text generation to serve models that process and generate text, audio, images,..."
date: 2026-09-28T22:02:06+05:30
tags: [AWS, SageMaker, vLLM, MultimodalAI, GenerativeAI]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/23/ML-21837-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Introduces vLLM-Omni Deep Learning Container for Multimodal Generation

AWS has released the vLLM-Omni Deep Learning Container (DLC) for Amazon SageMaker AI, extending vLLM capabilities beyond text generation to serve models that process and generate text, audio, images, and video.

## 🔍 Overview
The vLLM-Omni project provides a heterogeneous pipeline abstraction to coordinate multi-stage model workflows, including autoregressive and diffusion stages. The AWS vLLM-Omni DLC packages tracked vLLM-Omni releases into AWS images and adds routing middleware for SageMaker AI, offering OpenAI-compatible APIs and streaming outputs.

## 🧩 How it works
The solution uses specialized inference runtimes and DLCs to provide a consistent image-based path to AWS compute and managed inference services. Depending on the use case, it supports different streaming and inference modes:

*   **Bidirectional Streaming:** Uses a full-duplex WebSocket transported over HTTP/2. The client connects to the SageMaker Runtime endpoint on port 8443, and a sidecar forwards the connection to the vLLM-Omni native WebSocket route.
*   **Real-time Inference:** Used when applications require a direct response before constructing the next request.
*   **Asynchronous Inference:** Queues requests and utilizes Amazon S3 for input and output, allowing clients to poll for results.

## ⚙️ Key details
Supported modalities and models include:

| Capability | Example Model/Implementation |
| :--- | :--- |
| Text-to-Speech (TTS) | Qwen3-TTS |
| Speech-to-Text (STT) | Voxtral-Mini-4B Realtime |
| Image Generation | FLUX.2-klein-4B |
| Video Generation | Wan2.1-VACE-1.3B |

Technical specifications for deployment include the use of `ml.g6.xlarge` and `ml.g6e.xlarge` instance types in the US East (N. Virginia) AWS Region. The `SM_VLLM_MODEL` environment variable is used to specify which model to load into the container.

## 💡 Why it matters
Real-time voice applications—such as accessibility tools, interactive learning applications, customer service assistants, and voice agents—require responses without long silent pauses. This development enables a full voice pipeline where microphone audio is streamed to an STT model and the resulting response text is streamed back as speech via the vLLM-Omni DLC.

#AWS #SageMaker #vLLM #MultimodalAI #GenerativeAI

---

*Source: [Build real-time voice applications with vLLM-Omni on SageMaker AI – Part 1 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-real-time-voice-applications-with-vllm-omni-on-sagemaker-ai-part-1/)*
*Source: [Generate images and video with vLLM-Omni on SageMaker AI – Part 2 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/generate-images-and-video-with-vllm-omni-on-sagemaker-ai-part-2/)*
