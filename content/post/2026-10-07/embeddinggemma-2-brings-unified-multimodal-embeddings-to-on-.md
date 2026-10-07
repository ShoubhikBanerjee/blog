---
title: "EmbeddingGemma 2 Brings Unified Multimodal Embeddings to On‑Device AI"
slug: "embeddinggemma-2-brings-unified-multimodal-embeddings-to-ondevice-ai"
description: "- Today we are launching **EmbeddingGemma 2**, a unified multimodal embedding model that expands beyond text to include code, images, video, and audio."
date: 2026-10-07T22:09:50+05:30
tags: [EmbeddingGemma, MultimodalAI, EdgeAI]
categories: ["AI", "Machine Learning", "Multimodal AI", "Edge Computing"]
image: "https://storage.googleapis.com/gweb-uniblog-publish-prod/images/embeddinggemma2-banner_169.width-1300.png"
author: "Shoubhik Banerjee"
draft: false
---

# EmbeddingGemma 2 Brings Unified Multimodal Embeddings to On‑Device AI

## 🔍 Overview
- Today we are launching **EmbeddingGemma 2**, a unified multimodal embedding model that expands beyond text to include code, images, video, and audio.
- Built on the Gemma 4 architecture and released under the Apache 2.0 license, the model has 740 million parameters and is optimized for on‑device inference.

## 🧩 How it works
- EmbeddingGemma 2 shares the same text tokenizer and audio encoder as Gemma 4, allowing the two models to run together in a single pipeline with a lower combined memory footprint.
- The model uses **Matryoshka Representation Learning (MRL)** so output vectors can be truncated from 768 dimensions down to 512, 256, or 128 dimensions, giving up to **6× storage reduction** for local vector databases.

## ⚙️ Key details
- **Multimodal capabilities** – a single model can locate a specific video clip from a voice memo or search hours of audio recordings with a text query.
- **Benchmark performance** – achieves leading scores among sub‑1B multimodal embedders on benchmarks such as **MTEB Code** and **MAEB**, and matches or outperforms many larger models on text, vision, and audio tasks.
- **Code improvement** – code performance jumps 9.92 points on MTEB Code (68.76 → 78.68), making it suitable for local codebase indexing and semantic code search.
- **Modular size options**
  | Variant | Parameters |
  | ------- | ---------- |
  | Text‑only | 270 M |
  | Vision encoder (optional) | 170 M |
  | Audio encoder (optional) | 300 M |
- **Extended context** – 8 K token window (4× larger than EmbeddingGemma 1), enabling processing of up to **5.5 minutes of audio, 29 images, 58 video frames**, or interleaved combinations on local hardware.
- **On‑device efficiency** – with quantization, a Google Pixel 11 Pro uses ~191 MB active RAM for text‑only weights and ~567 MB for the full multimodal model.
- **Quality‑per‑parameter** – sets a new standard for sub‑1B models across image, video, document, and audio tasks, even outperforming specialist models more than twice its size.

## 🚀 Availability
- Model weights are available on **Hugging Face** and **Kaggle**; Gemini Enterprise Agent Platform Model Garden will add the model soon.
- Optimized versions can be found in the **LiteRT Community** on Hugging Face.
- Deploy on edge hardware with **Google AI Edge MediaPipe** (turnkey embedding, retrieval & decision) or **LiteRT** for custom integration.
- Build for browsers using **transformers.js** or **WebGPU**.
- Supported runtimes include **transformers, sentence‑transformers, MLX, vLLM, llama.cpp, SGLang, Ollama, LMStudio**.
- Store embedding vectors with **Qdrant**.
- Fine‑tuning guidance is provided by **Unsloth**.

## 💡 Why it matters
- Generating embeddings locally guarantees data privacy and reduces pipeline latency.
- Enables fully offline, cross‑modal search and retrieval, empowering developers to build on‑device RAG pipelines that understand complex multimodal data when paired with generative models such as Gemma 4.
- The developer community’s response to the original EmbeddingGemma exceeded expectations, with **more than 20 million downloads** used for smarter on‑device search tools and privacy‑first RAG pipelines.


![figure](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/embeddinggemma2-banner_169.width-200.format-webp.webp)

![figure](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/Massive_Text_Embedding_Benchmark_.width-100.format-webp.webp)

![figure](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/Massive_Audio_Embedding_Benchmark.width-100.format-webp.webp)

#EmbeddingGemma #MultimodalAI #EdgeAI

---

*Source: [EmbeddingGemma 2: an open, lightweight multimodal embedding model](https://blog.google/innovation-and-ai/technology/developers-tools/embeddinggemma-2/)*
