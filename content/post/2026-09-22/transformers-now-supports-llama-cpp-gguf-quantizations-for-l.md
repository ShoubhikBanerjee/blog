---
title: "Transformers Now Supports llama.cpp GGUF Quantizations for Local Inference"
slug: "transformers-now-supports-llama-cpp-gguf-quantizations-for-local-inference"
description: "The Transformers library now allows users to run llama.cpp GGUF quantizations using `from_pretrained`, enabling AI model generation directly on a user's own machine."
date: 2026-09-22T18:02:41+05:30
tags: [Transformers, llamacpp, GGUF, LocalAI, AppleSilicon]
categories: ["AI", "Machine Learning", "Local Inference", "Software Development"]
image: "https://huggingface.co/blog/assets/transformers_llama_cpp_quants/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Transformers Now Supports llama.cpp GGUF Quantizations for Local Inference

The Transformers library now allows users to run llama.cpp GGUF quantizations using `from_pretrained`, enabling AI model generation directly on a user's own machine.

## 🔍 Overview
GGUF is a widely used format for local inference developed by the llama.cpp team. It packages model weights and metadata—including tokenizer information and optional chat templates—into a single file. This format supports various quantization levels, allowing users to reduce the memory footprint by trading off some precision.

## 🧩 How it works
To achieve performance close to llama.cpp, Transformers reuses its underlying ggml kernels through the kernels library and reduces overhead in `generate`. 

* **Loading:** Users pass the Hub `model_id` and filename as `gguf_file` to `from_pretrained`.
* **Execution:** On Apple Silicon, when weights stay packed on Metal, Transformers automatically loads compatible ggml/Metal layer kernels and uses `ggml-org/ggml-attn` for attention implementation.
* **Fallbacks:** If the compatible kernel cannot be fetched, the system falls back to "sdpa" (which can also be forced by passing `attn_implementation="sdpa"`). Without a compatible quantization kernel, the loader dequantizes the model, which uses more memory.

## ⚙️ Key details
Initial focus is on local inference for Apple Silicon, starting with the Qwen3.5 architecture. Users can select different quantization variants based on their available memory:

| Quantization Variant | Description |
| :--- | :--- |
| Q4_K_M | Mixes tensor precisions; uses mostly 4-bit weights while keeping sensitive tensors at higher precision. |
| Q5_K_M | Recommended for users with more memory available. |
| Q6_K | Recommended for users with more memory available. |

## 🚀 Availability
Ready-to-use GGUF checkpoints are available on the Hub from several providers:
* ggml-org
* Unsloth
* LM Studio Community
* bartowski

## 💡 Why it matters
Running AI models locally has been made practical through llama.cpp and projects like MLX. The llama.cpp inference engine already powers tools such as Ollama, Jan, and LM Studio. Integrating this into Transformers makes it easier to run these models locally while allowing the same endpoint to be used by other clients that support the API.

#Transformers #llama.cpp #GGUF #LocalAI #AppleSilicon

---

*Source: [Transformers now runs llama.cpp quants](https://huggingface.co/blog/transformers-llama-cpp-quants)*
