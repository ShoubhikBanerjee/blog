---
title: "LLM Compressor v0.14.0 adds HIGGS quantization and MXFP4xFP8 checkpoint support"
slug: "llm-compressor-v0-14-0-adds-higgs-quantization-and-mxfp4xfp8-checkpoint-support"
description: "LLM Compressor has released version 0.14.0, introducing significant improvements to model optimization for vLLM deployment, including new quantization algorithms, pruning techniques, and support for..."
date: 2026-11-16T22:14:27+05:30
tags: [LLMCompressor, Quantization, vLLM, ModelOptimization, HIGGS, MXFP4]
categories: ["AI", "Machine Learning", "Model Optimization", "Quantization", "Deep Learning Infrastructure"]
image: "https://avatars.githubusercontent.com/u/136984999?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LLM Compressor v0.14.0 adds HIGGS quantization and MXFP4xFP8 checkpoint support

LLM Compressor has released version 0.14.0, introducing significant improvements to model optimization for vLLM deployment, including new quantization algorithms, pruning techniques, and support for mixed-precision formats.

## 🧩 How it works

The library provides comprehensive quantization and compression tools that integrate seamlessly with Hugging Face models. Key technical enhancements in v0.14.0 include:

*   **HIGGS mixed-precision quantization**: Collects layer-wise MSE sensitivity data and formulates an integer linear program to select an optimal mixed-precision configuration for a target average bitwidth. The resulting config can be passed to `oneshot` or `model_free_ptq`.
*   **Block-wise QAD**: A new `QADModifier` runs quantization-aware distillation after a weight-quantization modifier in the same recipe. It caches calibration inputs and the unquantized subgraph output as the teacher, then trains the quantized weights through compressed-tensors fake quantization without loading a separate teacher model.
*   **Layerwise compression and sequential offloading**: The sequential pipeline can decompress and compress one layer at a time, avoiding upfront whole-model conversion for large checkpoints. Onload/offload is managed manually with optional CPU staging and pinned memory.
*   **Faster observers for E8M0 formats**: The MSE and iMatrix observers gained exponential grid search and magnitude normalization for E8M0 scales, and the iMatrix observer now shares the MSE Triton kernel, delivering roughly 1.2-3.4x end-to-end speedups on tested models.
*   **MFPTQ SpinQuant rotations**: `SpinQuantConverter` applies offline R1/R2 Hadamard rotations directly to safetensors before model-free quantization, and `model_free_ptq` now accepts converter chains.
*   **MoNe expert pruning**: MoNe collapses low-saliency experts into constant "novice" vectors instead of removing them, keeping the router at full width while reducing expert compute.

## ⚙️ Key details

Several reporting and pruning features have been updated to support larger and more diverse model architectures:

*   **REAP reports and non-uniform pruning**: REAP now writes per-expert saliency reports, supports calibration-only report generation with `sparsity=0.0`, and accepts per-layer non-uniform expert sparsity. `n_routed_experts` is now recorded in config names, and GPT-OSS is skipped.
*   **MXFP6 and MXFP4xFP8 support**: Added MXFP6A8/MXFP6A16 schemes and examples, plus an MXFP4xFP8 example and refreshed quantization documentation.
*   **Broader hardware and model support**: The fused GPTQ Triton kernel now runs on Intel XPU, and MTP layers load through Transformers `MtpModel`. New checkpoints and examples include Nemotron 3.5 Super VL FP8, Zyphra Zaya1, Muse Spark, and Qwen3.6 MXFP4xFP8.
*   **Docs and community**: Added the Open Research Hub for community experiment results and a full Simplified Chinese README translation.

## 🚀 Availability

The Red Hat AI team has used LLM Compressor to produce a batch of production-ready quantized checkpoints optimized for Hopper GPUs:

| Checkpoint | Quantization Strategy | Resulting Size |
| :--- | :--- | :--- |
| Muse-Spark-Open-816B-A42B | Routed experts in MXFP4; attention and dense projections in FP8; ~4.2 bits per parameter | ~428 GB (down from ~1644 GB) |
| GLM-5.3 | Routed experts and dense MLPs in MXFP4; attention, shared experts, and MTP layer in FP8; ~4.5 bits per parameter | ~415 GB (down from ~1507 GB) |

Additional MXFP4xFP8 checkpoints are available for Qwen3.8-27B. Support for these formats in vLLM is available via PR vllm-project/vllm#64389 until it is merged.

#LLMCompressor #Quantization #vLLM #ModelOptimization #HIGGS #MXFP4

---

*Source: [vllm-project/llm-compressor](https://github.com/vllm-project/llm-compressor)*
