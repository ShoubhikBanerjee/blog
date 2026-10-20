---
title: "AnyLanguageModel 1.0 and Swift SDKs Enable Flexible Local and Hosted AI Inference"
slug: "anylanguagemodel-1-0-and-swift-sdks-enable-flexible-local-and-hosted-ai-inference"
description: "Language models have proven to be a powerful tool for building intelligence into products, and today the ecosystem gains a new set of tools."
date: 2026-10-20T22:03:21+05:30
tags: [FoundationModels, SwiftAI, LocalInference, HostedAI]
categories: ["AI", "Machine Learning", "Software Development", "AI Platforms", "Mobile Computing"]
image: "https://huggingface.co/blog/assets/anylanguagemodel-1-0/banner.png"
author: "Shoubhik Banerjee"
draft: false
---

# AnyLanguageModel 1.0 and Swift SDKs Enable Flexible Local and Hosted AI Inference

Language models have proven to be a powerful tool for building intelligence into products, and today the ecosystem gains a new set of tools.

## 🔍 Overview
Apple’s Swift ecosystem now includes **AnyLanguageModel 1.0**, **swift‑huggingface 1.0**, and **swift‑xet 1.0**. After a year of development and dozens of releases, the new stack supports both local and hosted inference, a shared API, and the Foundation Models API so developers can pick the model that fits each task.

## 🛠️ How it works
- A **shared API** lets you swap between system models, open‑weight models (llama.cpp, MLX, Core ML), and hosted providers without changing session code.
- **Tool calling** works with every provider, supporting nested `@Generable` types and arrays.
- **Image support** uses Foundation Models 27 syntax, allowing images to be attached to prompts on iOS, macOS, and visionOS 27.
- **Reasoning** is now part of the transcript; when you switch providers, reasoning blocks are automatically omitted if the new provider cannot replay them.
- **API keys** are supplied via a closure rather than a static string, enabling apps to fetch short‑lived tokens from their own server.
- The same Swift code runs on **Linux**, so you can use AnyLanguageModel on a server as well as on Apple devices.

## ⚙️ Key details
- **Local vs. hosted inference**: Both are supported, and hosted providers receive the same capabilities as local models—guided generation, streaming tool calls, and token‑usage reporting.
- **Supported platforms**: iOS, macOS, visionOS 27, and Linux.
- **Model compatibility**: On OS 27, AnyLanguageModel works with any model conforming to the Foundation Models `LanguageModel` protocol, including Core AI models.
- **Accelerated downloads**: swift‑huggingface and swift‑xet bring fast model downloads from the Hugging Face Hub directly into Swift apps.

### Model sizes and requirements
| Model | Format | Approx. Size | Runtime notes |
|-------|--------|--------------|---------------|
| GGUF (Q4_0) | GGUF | ~3.4 GB | Quantization‑aware training |
| GGUF (Q4_K_M) | GGUF | ~1.7 GB | |
| Qwen3.8 27B (MLX) | MLX | ~16 GB (4‑bit) | Fits on a Mac with ≥32 GB memory |
| GLM‑5.3 (Z.ai) | BF16 | ~1.5 TB | Requires four maxed‑out Mac Studios |

## 🚀 Availability
- **AnyLanguageModel 1.0**, **swift‑huggingface 1.0**, and **swift‑xet 1.0** are released and ready for integration.
- Hosted model support has been expanded this year; the same features available to local models are now offered by inference providers.
- Migration guidance is provided in the release notes for each package to help developers update existing apps.
- Community feedback and contributions directly shaped several major features; contributors are thanked for making AnyLanguageModel more useful to app developers.

## 💡 Why it matters
- Developers can now choose the most suitable model—small local models for quick on‑device starts or large hosted models for heavyweight tasks—without rewriting code.
- The unified API lowers the barrier to experimenting with different providers and capabilities such as tool calling and image‑augmented prompts.
- Upcoming additions include “models that decide” and “models that listen,” extending the range of capabilities reachable through the same Swift‑first workflow.


![figure](https://huggingface.co/blog/assets/omlx/omlx-hf.jpg)

![figure](https://huggingface.co/blog/assets/transformers-to-mlx/thumbnail.jpg)

#FoundationModels #SwiftAI #LocalInference #HostedAI

---

*Source: [AnyLanguageModel 1.0: One Year of Local Models on Apple Platforms](https://huggingface.co/blog/anylanguagemodel-1-0)*
