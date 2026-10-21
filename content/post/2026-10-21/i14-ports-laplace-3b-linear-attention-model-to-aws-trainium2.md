---
title: "i14 Ports Laplace 3B Linear Attention Model to AWS Trainium2"
slug: "i14-ports-laplace-3b-linear-attention-model-to-aws-trainium2"
description: "AI research company i14 has updated the implementation of Laplace 3B, a linear attention alternative to traditional transformer architectures, by bringing the model to AWS Trainium2 using TorchNeuron..."
date: 2026-10-21T12:01:55+05:30
tags: [AWS, Trainium2, LinearAttention, LLM, i14]
categories: ["AI", "Machine Learning", "AI Infrastructure", "Model Architecture"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/14/ML-21817-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# i14 Ports Laplace 3B Linear Attention Model to AWS Trainium2

AI research company i14 has updated the implementation of Laplace 3B, a linear attention alternative to traditional transformer architectures, by bringing the model to AWS Trainium2 using TorchNeuron Native.

## 💡 Why it matters
Most large language models (LLMs) utilize transformer architectures with softmax attention, which causes the key-value (KV) cache to grow as conversation or document context increases. This growth can lead to:
* Reduced concurrency
* Increased serving costs
* The need for agentic applications to discard useful history

## 🧩 How it works
Laplace 3B is a 24-layer decoder that replaces softmax attention with Simple Gated Linear Attention (GLA). 

* **Linear Attention:** Reorganizes computation around a recurrent state updated for each token, changing training attention complexity from O(T2) to O(T).
* **Context Compression:** GLA compresses prior context into a fixed-size matrix state.
* **Fixed State:** The inference state remains fixed at 29.5 MB per sequence, independent of context length.

## ⚙️ Key details
Working with the AWS Generative AI Innovation Center (GenAIIC), i14 transitioned the model from GPU-optimized Triton kernels to the TorchNeuron Native PyTorch backend. Technical adjustments included:

* **Kernel Optimization:** The team replaced the `fused_chunk_simple_gla` Triton kernel with standard PyTorch operators, using 16 chunks of 128 tokens to match the 128 partitions of the NeuronCore on-chip buffer.
* **Compiler Compatibility:** The 16 chunk steps of the GLA recurrence were statically unrolled to fit the on-chip memory limits and graph-size of the compiler.
* **Throughput Improvements:** Two `all_to_all` collectives in MuonFSDP2 increased throughput by 1.63 times and reduced per-rank traffic by 24 times.

### Hardware Specifications
Laplace 3B was deployed on a `trn2.48xlarge` instance, which features:

| Component | Specification |
| :--- | :--- |
| Chips | 16 Trainium2 chips |
| NeuronCores | 64 logical NeuronCores |
| Connectivity | NeuronLink-v3 |
| SBUF | 28 MiB State Buffer with 128 partitions per NeuronCore |
| PSUM | 2 MiB partial-sum buffer wired to a 128×128 systolic Tensor Engine |

### Performance Metrics
On one `trn2.48xlarge` instance, the model achieved the following:
* **Training Speed:** Approximately 120,000 tokens per second.
* **Inference Throughput:** 11,544 output tokens per second across 1,280 concurrent sequences.

#AWS #Trainium2 #LinearAttention #LLM #i14

---

*Source: [Beyond the KV cache: Training and serving i14’s Laplace 3B linear attention model on AWS Trainium2 with native PyTorch | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/beyond-the-kv-cache-training-and-serving-i14s-laplace-3b-linear-attention-model-on-aws-trainium2-with-native-pytorch/)*
