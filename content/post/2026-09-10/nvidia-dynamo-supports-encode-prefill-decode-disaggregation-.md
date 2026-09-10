---
title: "NVIDIA Dynamo Supports Encode-Prefill-Decode Disaggregation for Multimodal Model Inference"
slug: "nvidia-dynamo-supports-encode-prefill-decode-disaggregation-for-multimodal-model-inference"
description: "NVIDIA Dynamo, an open source inference framework for distributed environments, now supports Encode-Prefill-Decode (EPD) disaggregation. This optimization technique improves multimodal model..."
date: 2026-09-10T12:09:25+05:30
tags: [NVIDIA, Dynamo, LLM, MultimodalAI, Inference]
categories: ["AI", "Machine Learning", "Computer Vision", "AI Infrastructure"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/multimodal-dynamo-660x370.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Dynamo Supports Encode-Prefill-Decode Disaggregation for Multimodal Model Inference

NVIDIA Dynamo, an open source inference framework for distributed environments, now supports Encode-Prefill-Decode (EPD) disaggregation. This optimization technique improves multimodal model performance by separating the vision encoder stage from the prefill and decode stages.

## 🧩 How it works

Dynamo implements EPD serving by separating encoder and PD (prefill-decode) worker roles. Instead of running these phases with tightly coupled scheduling, they are treated as independently scalable stages:

* **Encoder Workers**: Produce vision embeddings.
* **PD Workers**: Consume those embeddings and run the LLM.
* **Data Transfer**: The NVIDIA Inference Transfer Library (NIXL) is used to pass embeddings from encoder workers to PD workers.

## ⚙️ Key details

There are three primary placement options for these workers:

| Placement Option | Description |
| :--- | :--- |
| Aggregated | Each GPU runs a single worker managing encoding, prefill, and decode for the entire request lifecycle. |
| Colocated Encoder | Each GPU runs one or more encoder workers alongside one PD worker; generally the better fit for homogeneous clusters. |
| Disaggregated Encoder | Encoder workers are placed on a lower-cost GPU tier while the primary GPU tier hosts PD workers. |

In a test environment, two NVIDIA RTX 6000D GPUs were used for encoder workers, while four NVIDIA GB200 GPUs handled the PD workers. This configuration reserves the GB200 GPUs for the more memory- and compute-intensive LLM workload.

## 💡 Why it matters

EPD disaggregation isolates encoder work, which allows text requests to skip waiting for the encoder. This leads to improvements in batching, memory efficiency, and overall throughput. 

Performance gains include:
* Up to 5x faster time to first token (TTFT).
* Up to 7x faster end-to-end response time.

The technique is most effective under the following conditions:
* Image-heavy prompts.
* Short-to-medium outputs.
* Quantized mixture-of-experts (MoE) and lower-precision models (e.g., Qwen3.5 122B A10B NVFP4).
* Scenarios where vision encoding accounts for a significant share of processing time or limits throughput.

Large dense models see less gain from this optimization.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/how-nvidia-dynamo-handles-multimodal-request-aggregated-versus-epd.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/three-multimodal-encode-placement-options.webp)

#NVIDIA #Dynamo #LLM #MultimodalAI #Inference

---

*Source: [When to Use Encode-Prefill-Decode Disaggregation to Accelerate Multimodal Model Serving | NVIDIA Technical Blog](https://developer.nvidia.com/blog/when-to-use-encode-prefill-decode-disaggregation-to-accelerate-multimodal-model-serving/)*
