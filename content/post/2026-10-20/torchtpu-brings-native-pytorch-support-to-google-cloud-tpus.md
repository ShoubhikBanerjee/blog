---
title: "TorchTPU Brings Native PyTorch Support to Google Cloud TPUs"
slug: "torchtpu-brings-native-pytorch-support-to-google-cloud-tpus"
description: "With TorchTPU, a native PyTorch backend, TPU is now just another device. The integration lets Transformers, Diffusers and custom kernels run natively on Google’s Tensor Processing Units (TPUs)."
date: 2026-10-20T22:03:21+05:30
tags: [PyTorch, TPU, TorchTPU, Transformers, Diffusers]
categories: ["AI", "Machine Learning", "Deep Learning", "Hardware Acceleration", "Cloud Computing"]
image: "https://huggingface.co/blog/assets/hf-torchtpu/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# TorchTPU Brings Native PyTorch Support to Google Cloud TPUs

With TorchTPU, a native PyTorch backend, TPU is now just another device. The integration lets Transformers, Diffusers and custom kernels run natively on Google’s Tensor Processing Units (TPUs).

## 🔍 Overview
- TPU stands for Tensor Processing Unit and is Google’s own AI accelerator.\
- Google has been designing TPUs for about ten years and uses them for its models, including Gemini.\
- TPUs are available on Google Cloud, from a single chip up to pods of thousands of chips.

## 🧩 How it works
- **TorchTPU** adds TPU as a new backend to PyTorch.\
- It includes **Pallas kernels** tuned for TPUs, support for distributed training, and a `torch.compile` integration for extra speed.\
- TPU kernels are written in **Pallas**, giving low‑level hardware control.\
- Additional kernels can be imported from the **Tokamax library**.\
- Installation on a TPU VM is a single command:
  ```bash
  pip install torch-tpu --extra-index-url https://download.pytorch.org/whl/cpu
  ```
- To load a model on a TPU, set `device_map="tpu"`.\
- The **TensorParallelConfig** can be passed to `from_pretrained` to shard the model across chips, so the full model never has to fit in one place.

## ⚙️ Key details
- **Transformers v5** is built to be the source of truth for model definitions, enabling them to run anywhere, including TPUs.\
- **Diffusers** now treats TPU as a first‑class device.\
- Example runs on a Cloud TPU v6e‑4 with 4 chips (TP=4), bf16 precision, batch size 1.\
- At batch size 64, decoding is **21.5× faster** on Qwen3‑30B‑A3B and **12.8× faster** on Gemma 4 26B‑A4B.\
- Decode throughput comparisons on a TPU v6e‑8 show Hub kernels outperforming the default implementation.

## 🚀 Availability
- The **Kernels Hub** provides ready‑to‑use TPU kernels.\
- TorchTPU is publicly installable via `pip`.\
- A nightly CI on TPU is being added, with results to appear in the Transformers dashboard.

## 💡 Why it matters
- By making TPU a first‑class device in PyTorch, developers can train and serve large language models on Google Cloud without rewriting code.\
- Sharding with `TensorParallelConfig` removes the need for a single device to hold the entire model, enabling very large models to run on TPU pods.

### Component Summary
| Component | Role |
|-----------|------|
| TorchTPU | Adds TPU as a PyTorch backend |
| Pallas kernels | Tuned TPU kernels, low‑level control |
| Tokamax library | Additional kernels that can be imported |



![figure](https://huggingface.co/buckets/huggingface/hf-torchtpu-blog-assets/resolve/images/kernel-ragged-dot-speedup.png)

![figure](https://huggingface.co/buckets/huggingface/hf-torchtpu-blog-assets/resolve/images/tpu-ci-dashboard.png)

![figure](https://huggingface.co/buckets/huggingface/hf-torchtpu-blog-assets/resolve/images/banner.jpg)

#PyTorch #TPU #TorchTPU #Transformers #Diffusers

---

*Source: [Hugging Face ❤️ TorchTPU: TPUs, Natively](https://huggingface.co/blog/hf-torchtpu)*
