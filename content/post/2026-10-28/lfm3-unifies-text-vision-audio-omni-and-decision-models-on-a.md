---
title: "LFM3 Unifies Text, Vision, Audio, Omni, and Decision Models on a 2‑Billion‑Parameter Backbone"
slug: "lfm3-unifies-text-vision-audio-omni-and-decision-models-on-a-2billionparameter-backbone"
description: "The latest release, LFM3, is the new generation of Liquid Foundation Models that unifies text, vision, audio, omni, and decision capabilities on a shared ~2 B‑parameter backbone."
date: 2026-10-28T06:05:03+05:30
tags: [LiquidFoundationModels, MultimodalAI, EdgeAI, ModelOptimization]
categories: ["AI", "Machine Learning", "Multimodal AI", "Edge Computing", "Artificial Intelligence"]
image: "https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/wEKXxH6qGa7vmHjn5KA-W.png"
author: "Shoubhik Banerjee"
draft: false
---

# LFM3 Unifies Text, Vision, Audio, Omni, and Decision Models on a 2‑Billion‑Parameter Backbone

The latest release, LFM3, is the new generation of Liquid Foundation Models that unifies text, vision, audio, omni, and decision capabilities on a shared ~2 B‑parameter backbone.

## 🔍 Overview
- LFM3 is built to be the starting point for specialized intelligence.
- It brings text, vision, audio, omni, and decision models onto one shared backbone, each in the ~2 B‑parameter range.
- Every modality model branches from LFM3-1.7B-Base.

## 🧩 How it works
- **Tri‑hybrid architecture**: 13 gated short convolutions (kernel size 7), 5 sliding‑window attention layers with a 256‑token window, and 6 global attention layers.
- **Head‑wise gated attention**: a sigmoid gate scales each head’s output, allowing a head to switch off when it adds nothing.
- **Partial RoPE**: global attention layers rotate only the highest‑frequency half of each head, keeping the other half invariant to distance.
- **Hardware‑in‑the‑loop architecture search** redesigns the model for agentic use cases and now covers 14 device and backend combinations, from phones and a Raspberry Pi 5 to laptops, cloud CPUs/GPUs, and the Qualcomm Hexagon NPU.

## ⚙️ Key Details
- **Parameter efficiency**: LFM3‑1.7B outperforms LFM2.5‑2.6B while using 35 % fewer parameters.
- **Speed**: With an 8 K‑token context it is about 25 % faster per parameter than LFM2‑1.2B on edge devices.
- **Context window**: The text model supports a 256 K‑token window; the final 3.5 T pre‑training tokens extend this window.
- **Pre‑training**: 22 T tokens using the same 128 K vocabulary as LFM2.5‑8B‑A1B, with the last 3.5 T tokens emphasizing agentic traces and tool calls.
- **Edge readiness**:
  - Text model fits in ~1 GB at 4‑bit precision.
  - Vision encoder combines convolution and attention, using 3× less compute than the SigLIP2 encoder in previous LFM VL models.
  - The 164 M‑parameter vision encoder matches Qwen3.5‑2B’s vision accuracy while requiring 2.2× fewer FLOPs.
  - LiquidCodec audio tokenizer turns generated tokens into speech at ~87× real‑time on a single CPU thread on Apple M4 Max and supports streaming decoding.
- **Fine‑tuning**: Any modality model can be fine‑tuned on a single GPU and deployed where the application runs.

### Model variants (all derived from LFM3‑1.7B‑Base)
| Variant | Modality | Notable features |
|---|---|---|
| Text | Text | ~1 GB at 4‑bit, 256 K context window, suitable for on‑device agents |
| Vision | Vision | Convolution + attention, 3× less compute than SigLIP2, matches Qwen3.5‑2B accuracy with 2.2× fewer FLOPs |
| Audio | Audio | Uses LiquidCodec tokenizer, ~87× real‑time speech generation on Apple M4 Max, streaming decoding |
| Omni | Omni | First omni model sharing the same backbone |
| Decision | Decision | Shares backbone, optimized for agentic tasks |

## 🚀 Availability
- Models can be fine‑tuned on a single GPU and deployed on the target hardware, including phones, Raspberry Pi 5, laptops, cloud CPUs/GPUs, and the Qualcomm Hexagon NPU.
- Recommended for local agents, tool calling, structured outputs, or as a base for domain‑specific fine‑tuning.

## 💡 Why it matters
- The shared backbone provides more capability per parameter, allowing a 1.7 B‑parameter model to outperform larger predecessors.
- Unified architecture across modalities reduces the need for separate model families.
- Edge‑centric design—small size, fast inference, long context—enables advanced agentic tasks to run locally without cloud dependence.

![figure](https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/iZQBqXVZfrcUNCklF4eAs.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/6RfJINOKr6Ay2kHCPR-mz.png)

#LiquidFoundationModels #MultimodalAI #EdgeAI #ModelOptimization

---

*Source: [Build specialized multimodal models with LFM3](https://huggingface.co/blog/LiquidAI/lfm3)*
