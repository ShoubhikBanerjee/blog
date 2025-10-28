---
title: "Google Cloud C4 Delivers 70% TCO Improvement with GPT OSS on Intel Xeon 6"
description: "Intel and Hugging Face demonstrate 1.7x performance improvement and 70% TCO
advantage running GPT OSS Large Language Model on Google Cloud C4 VMs with Intel Xeon 6
processors compared to previous-generation C3 instances."
date: 2025-10-28T01:05:01.796582+05:30
tags: ["Google Cloud", "Intel Xeon 6", "GPT OSS", "Large Language Models", "MoE", "CPU Inference", "TCO", "Performance Optimization", "Hugging Face", "Cloud Computing"]
categories: ["Cloud Computing", "AI/ML", "Performance Optimization"]
image: "https://huggingface.co/datasets/Intel/blog/resolve/main/gpt-oss-on-intel-xeon/gpt_oss_expert.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Google Cloud C4 Delivers 70% TCO Improvement with GPT OSS on Intel Xeon 6

![GPT OSS Expert Architecture](https://huggingface.co/datasets/Intel/blog/resolve/main/gpt-oss-on-intel-xeon/gpt_oss_expert.png)
*Optimized expert execution in GPT OSS MoE architecture eliminates redundant computations*

Intel and Hugging Face collaborated to demonstrate the real-world value of upgrading to Google's
 latest **C4** Virtual Machine (VM) running on Intel® Xeon® 6 processors (codenamed Granite
Rapids). The benchmark focused on text generation performance improvements with OpenAI's GPT OSS
 Large Language Model (LLM).

The results showcase impressive gains with a **1.7x improvement** in Total Cost of Ownership
(TCO) over previous-generation Google **C3** VM instances, delivering:

- **1.4x to 1.7x** TPOT throughput/vCPU/dollar improvement
- **Lower hourly pricing** compared to C3 VMs

## 🧩 Introduction

GPT OSS represents an open-source Mixture of Experts (MoE) model from OpenAI. MoE architecture
utilizes specialized "expert" sub-networks with a "gating network" that determines which experts
 process specific inputs. This design enables efficient model capacity scaling without linear
compute cost increases, allowing different experts to develop specialized skills for diverse data distributions.

The architecture's efficiency makes CPU inference viable even with large parameter counts, as
only small expert subsets activate per token.

Intel and Hugging Face collaborated on expert execution optimization (PR #40304), eliminating
redundant computations where every expert previously processed all tokens. The optimization
directs each expert to process only routed tokens, removing FLOP waste and improving utilization.

## ⚙️ Benchmark Scope & Hardware

The benchmark evaluated GPT OSS under controlled, repeatable generation workloads to isolate
architectural differences between GCP **C4** VMs (Intel Xeon 6 processors) and GCP **C3** VMs
(4th Gen Intel Xeon Processors). Focus areas included steady-state decoding latency and
end-to-end normalized throughput with increasing batch sizes while maintaining fixed sequence lengths.

### 📋 Configuration Summary

- **Model**: unsloth/gpt-oss-120b-BF16
- **Precision**: bfloat16
- **Task**: Text generation
- **Input length**: 1024 tokens (left-padded)
- **Output length**: 1024 tokens
- **Batch sizes**: 1, 2, 4, 8, 16, 32, 64
- **Enabled features**:
  - Static KV cache - SDPA attention backend
- **Metrics**: Throughput (total generated tokens per second across batch)

### 🖥️ Hardware Under Tes

| Instance | Architecture | vCPUs |
| --- | --- | --- |
| **C3** | 4th Gen Intel Xeon processor (SPR) | 172 |
| **C4** | Intel Xeon 6 processor (GNR) | 144 |

## ☁️ Instance Creation

### C3 Configuration

Visit **Google Cloud Console** and create a VM under your project:

1. Select **C3** in Machine configuration, specify **c3-standard-176**
2. Set CPU platform and enable **all-core turbo** for stable performance 3. Configure OS and storage as required
4. Maintain default configurations for other settings

![C3 Configuration](https://huggingface.co/datasets/Intel/blog/resolve/main/gpt-oss-on-intel-xeon/spr.png)
*C3 instance configuration with 176 vCPUs*

### C4 Configuration

Follow similar steps for **C4** instance creation:

1. Select **C4** in Machine configuration, specify **c4-standard-144**
2. Configure CPU platform and enable all-core turbo 3. Apply same OS and storage configuration as C3
4. Create the 144 vCPU instance

![C4 Configuration](https://huggingface.co/datasets/Intel/blog/resolve/main/gpt-oss-on-intel-xeon/gnr.png)
*C4 instance configuration with 144 vCPUs*

## 🛠️ Environment Setu

SSH into the instance and install Docker. Follow these reproducible setup steps:

1. **Clone repository**: `git clone https://github.com/huggingface/transformers.git`2. **Navigate and checkout**: `cd transformers/ && git checkout
26b65fb5168f324277b85c558ef8209bfceae1fe`
3. **Build Docker image**: `cd docker/transformers-intel-cpu/ && sudo docker build . -t <your_docker_image_tag>`
4. **Run container**: `sudo docker run -it --rm --privileged -v
/home/<your_home_folder>:/workspace <your_docker_image_tag> /bin/bash`

Inside the container:
1. **Install transformers**: `pip install
git+https://github.com/huggingface/transformers.git@26b65fb5168f324277b85c558ef8209bfceae1fe`2. **Install PyTorch**: `pip install torch==2.8.0 torchvision torchaudio --index-url
https://download.pytorch.org/whl/cpu`

## 📊 Benchmark Procedure

For each batch size:

1. Build fixed-length 1024-token left-padded batch 2. Execute single warm-up round
3. Set `max_new_tokens=1024` and measure total latency
4. Calculate: `throughput = (OUTPUT_TOKENS * batch_size) / total_latency`

Execute with: `numactl -l python benchmark.py`

```python
import os import time
import torch from datasets import load_dataset
from transformers import AutoModelForCausalLM, AutoTokenizer

INPUT_TOKENS = 1024 OUTPUT_TOKENS = 1024

def get_inputs(tokenizer, batch_size):
    dataset = load_dataset("ola13/small-the_pile", split="train") tokenizer.padding_side = "left"
    selected_texts = []

    for sample in dataset:
        input_ids = tokenizer(sample["text"], return_tensors="pt").input_ids
        if len(selected_texts) == 0 and input_ids.shape[-1] >= INPUT_TOKENS:
            selected_texts.append(sample["text"]) elif len(selected_texts) > 0:
            selected_texts.append(sample["text"]) if len(selected_texts) == batch_size:
            break

    return tokenizer(selected_texts, max_length=INPUT_TOKENS,
                    padding="max_length", truncation=True, return_tensors="pt")

def run_generate(model, inputs, generation_config):
    inputs["generation_config"] = generation_config model.generate(**inputs)  # warm up

    pre = time.time() model.generate(**inputs)
    latency = (time.time() - pre) return latency

def benchmark(model, tokenizer, batch_size, generation_config):
    inputs = get_inputs(tokenizer, batch_size)

    generation_config.max_new_tokens = 1 generation_config.min_new_tokens = 1
    prefill_latency = run_generate(model, inputs, generation_config)

    generation_config.max_new_tokens = OUTPUT_TOKENS generation_config.min_new_tokens = OUTPUT_TOKENS
    total_latency = run_generate(model, inputs, generation_config)

    decoding_latency = (total_latency - prefill_latency) / (OUTPUT_TOKENS - 1)
    throughput = OUTPUT_TOKENS * batch_size / total_latency

    return prefill_latency, decoding_latency, throughput

if __name__ == "__main__":
    model_id = "unsloth/gpt-oss-120b-BF16" tokenizer = AutoTokenizer.from_pretrained(model_id)
    model_kwargs = {"dtype": torch.bfloat16} model = AutoModelForCausalLM.from_pretrained(model_id, **model_kwargs)
    model.config._attn_implementation="sdpa"

    generation_config = model.generation_config generation_config.do_sample = False
    generation_config.cache_implementation="static"

    for batch_size in [1, 2, 4, 8, 16, 32, 64]:
        print(f"---------- Run generation with batch size = {batch_size} ----------", flush=True)
        prefill_latency, decoding_latency, throughput = benchmark(model, tokenizer, batch_size, generation_config)
        print(f"throughput = {throughput}", flush=True)
```

## 📈 Results

### 🎯 Normalized Throughput per vCPU

Intel Xeon 6 processor-powered **C4** consistently outperforms **C3** with **1.4x to 1.7×
throughput per-vCPU** across batch sizes up to 64.

**Formula**: `normalized_throughput_per_vCPU = (throughput_C4 / vCPUs_C4) / (throughput_C3 /
vCPUs_C3)`

![Throughput per vCPU](https://huggingface.co/datasets/Intel/blog/resolve/main/gpt-oss-on-intel-xeon/throughput-gpt-oss-per-vcpu.png)
*C4 demonstrates consistent 1.4x-1.7x throughput advantage per vCPU across all batch sizes*

### 💰 Cost & TCO Analysis

At batch size 64, **C4** delivers **1.7× per-vCPU throughput** compared to **C3**. With near
price parity per vCPU, this yields a **1.7× TCO advantage** - C3 would require 1.7× the spending
 for equivalent generated token volume.

**TCO Calculation**: `throughput_ratio = 1.7 ⇒ TCO_C3/TCO_C4 ≈ 1.7`

![Throughput per Dollar](https://huggingface.co/datasets/Intel/blog/resolve/main/gpt-oss-on-intel-xeon/throughput-gpt-oss-per-dollar.png)
*Cost efficiency comparison shows C4's superior performance per dollar invested*

---

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/gpt-oss-on-intel-xeon*

## 🏁 Conclusion

Google Cloud **C4** VMs powered by Intel Xeon 6 processors deliver impressive performance gains
and superior cost efficiency for large MoE inference compared to previous-generation **C3** VMs.
 The GPT OSS benchmarks demonstrate combined benefits of higher throughput, lower latency, and
reduced operational costs.

These results highlight how targeted framework optimizations from Intel and Hugging Face enable
efficient serving of large MoE models on next-generation general-purpose CPUs, making advanced
AI capabilities more accessible and cost-effective for enterprises.

**Key Takeaways**:
- **70% TCO improvement** with C4 over C3 instances
- **1.4x-1.7x performance gains** across different batch sizes
- **Framework optimizations** crucial for MoE model efficiency
- **CPU inference viability** for large-scale AI workloads

---

*#GOOGLECLOUD #INTEL #CPU #AI #LLM #MOE #PERFORMANCE #TCO #HUGGINGFACE*

