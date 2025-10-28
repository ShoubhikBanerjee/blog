---
title: "DeepSeek-V3.2-Exp: Revolutionary Sparse Attention Architecture for Long-Context AI"
description: "Exploring DeepSeek-AI's experimental model featuring groundbreaking sparse
attention mechanisms that deliver substantial efficiency improvements for long-context scenarios
 while maintaining output quality."
date: 2025-10-28T01:22:09.976694+05:30
tags: ["DeepSeek", "Sparse Attention", "Transformer Architecture", "Large Language Models", "AI Efficiency", "Long Context", "Open Source AI", "Machine Learning", "CUDA Kernels", "Model Optimization"]
categories: ["Artificial Intelligence", "Machine Learning", "Open Source"]
image: "https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/logo.svg?raw=true"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🤖 DeepSeek-V3.2-Exp: Revolutionary Sparse Attention Architecture

![DeepSeek-V3 Logo](https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/logo.svg?raw=true)
*The latest experimental model from DeepSeek-AI showcasing innovative sparse attention
mechanisms*

---

[![Homepage](https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/badge.svg?raw=true)](h
ttps://deepseek.com)
[![Chat](https://img.shields.io/badge/🤖%20Chat-DeepSeek%20V3-536af5?color=536af5&logoColor=whit
e)](https://chat.deepseek.com)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-DeepSeek%20AI-ffc107
?color=ffc107&logoColor=white)](https://huggingface.co/deepseek-ai)

[![Discord](https://img.shields.io/badge/Discord-DeepSeek%20AI-7289da?logo=discord&logoColor=whi
te&color=7289da)](https://discord.gg/deepseek-ai)
[![WeChat](https://img.shields.io/badge/WeChat-DeepSeek%20AI-brightgreen?logo=wechat&logoColor=w
hite)](https://wechat.deepseek.com)
[![Twitter](https://img.shields.io/badge/Twitter-deepseek_ai-white?logo=x&logoColor=white)](http
s://twitter.com/deepseek_ai)

[![License](https://img.shields.io/badge/License-MIT-f5de53?&color=f5de53)](https://opensource.o
rg/licenses/MIT)

## 🚀 Introduction

DeepSeek-AI has officially released **DeepSeek-V3.2-Exp**, an experimental version that
represents a significant leap forward in transformer architecture efficiency. This
groundbreaking model serves as an intermediate step toward next-generation AI systems, building
upon the robust foundation of V3.1-Terminus while introducing the revolutionary **DeepSeek
Sparse Attention (DSA)** mechanism.

The experimental release focuses on optimizing computational efficiency for long-context
scenarios, addressing one of the most challenging aspects of modern language model deployment.
Through innovative sparse attention mechanisms, V3.2-Exp delivers substantial improvements in
both training and inference efficiency without compromising output quality.

## ⚡ Performance & Efficiency Breakthrough

![Cost Efficiency
Chart](https://huggingface.co/deepseek-ai/DeepSeek-V3.2-Exp/resolve/main/assets/cost.png)
*Performance comparison showing DeepSeek Sparse Attention efficiency gains*

### 🎯 Key Achievements

- **Fine-grained sparse attention**: First-time achievement of precise sparse attention
mechanisms
- **Substantial efficiency improvements**: Significant gains in long-context training and
inference
- **Quality preservation**: Virtually identical model output quality maintained
- **Rigorous evaluation**: Training configurations deliberately aligned with V3.1-Terminus for
fair comparison

### 📊 Benchmark Performance Comparison

| Benchmark | DeepSeek-V3.1-Terminus | DeepSeek-V3.2-Exp |
|-----------|-------------------------|-------------------|
| **Reasoning Mode w/o Tool Use** | | |
| MMLU-Pro | 85.0 | 85.0 |
| GPQA-Diamond | 80.7 | 79.9 |
| Humanity's Last Exam | 21.7 | 19.8 |
| LiveCodeBench | 74.9 | 74.1 |
| AIME 2025 | 88.4 | 89.3 |
| HMMT 2025 | 86.1 | 83.6 |
| Codeforces | 2046 | 2121 |
| Aider-Polyglot | 76.1 | 74.5 |
| **Agentic Tool Use** | | |
| BrowseComp | 38.5 | 40.1 |
| BrowseComp-zh | 45.0 | 47.9 |
| SimpleQA | 96.8 | 97.1 |
| SWE Verified | 68.4 | 67.8 |
| SWE-bench Multilingual | 57.8 | 57.9 |
| Terminal-bench | 36.7 | 37.7 |

## 🔧 Running DeepSeek-V3.2-Exp Locally

### 🤗 HuggingFace Implementation

DeepSeek provides comprehensive inference demo code in the `inference` folder, enabling quick
community adoption and architectural understanding.

**Step 1: Convert Model Weights**
```bash
cd inference
export EXPERTS=256
python convert.py --hf-ckpt-path ${HF_CKPT_PATH} --save-path ${SAVE_PATH} --n-experts ${EXPERTS}
 --model-parallel ${MP}
```

**Step 2: Launch Interactive Chat**
```bash
export CONFIG=config_671B_v3.2.json
torchrun --nproc-per-node ${MP} generate.py --ckpt-path ${SAVE_PATH} --config ${CONFIG}
--interactive
```

### 🚀 SGLang Deployment

#### Docker Installation Options
```bash
# H200 GPUs
docker pull lmsysorg/sglang:dsv32

# MI350 GPUs (ROCm)
docker pull lmsysorg/sglang:dsv32-rocm

# NPUs (Ascend)
docker pull lmsysorg/sglang:dsv32-a2
docker pull lmsysorg/sglang:dsv32-a3
```

#### Launch Configuration
```bash
python -m sglang.launch_server --model deepseek-ai/DeepSeek-V3.2-Exp --tp 8 --dp 8
--enable-dp-attention
```

### ⚡ vLLM Integration

vLLM provides day-0 support for DeepSeek-V3.2-Exp with optimized inference capabilities.
Detailed implementation recipes are available in the [vLLM
documentation](https://docs.vllm.ai/en/latest/models/supported_models.html).

## 🧩 Open-Source Kernel Ecosystem

DeepSeek maintains a commitment to open-source innovation through specialized kernel libraries:

### 📚 Research-Focused Kernels
- **[TileLang](https://github.com/deepseek-ai/TileLang)**: Enhanced readability and
research-purpose design kernels

### 🏎️ High-Performance CUDA Kernel
- **[DeepGEMM](https://github.com/deepseek-ai/DeepGEMM)**: Indexer logit kernels with paged
version support
- **[FlashMLA](https://github.com/deepseek-ai/FlashMLA)**: Optimized sparse attention kernels

## 📄 License & Usage

This repository and model weights are licensed under the **[MIT
License](https://opensource.org/licenses/MIT)**, ensuring maximum accessibility for research and
 commercial applications.

## 📖 Citation

```bibtex
@misc{deepseekai2024deepseekv32,
    title={DeepSeek-V3.2-Exp: Boosting Long-Context Efficiency with DeepSeek Sparse Attention},
    author={DeepSeek-AI},
    year={2025},
}
```

## 📞 Contact & Support

For technical questions, issues, or collaboration inquiries, please:
- 🐛 **Raise an issue** on the GitHub repository
- 📧 **Email us** at [service@deepseek.com](mailto:service@deepseek.com)

---

## 🙌 Credits

*Originally posted at: https://huggingface.co/deepseek-ai/DeepSeek-V3.2-Exp*

## 🏁 Conclusion

DeepSeek-V3.2-Exp represents a pivotal advancement in transformer architecture, successfully
demonstrating that sparse attention mechanisms can deliver substantial efficiency improvements
without sacrificing model quality. The experimental release validates the potential for
next-generation AI systems that can handle longer contexts more efficiently, paving the way for
more practical and cost-effective large language model deployments.

Key takeaways include the successful implementation of fine-grained sparse attention, maintained
 performance parity with established models, and comprehensive open-source tooling that enables
community adoption and further research. This release positions DeepSeek at the forefront of
efficient AI architecture development.

_#DEEPSEEK #AI #SPARSEATTENTION #TRANSFORMERS #LLMEFFICIENCY #OPENSOURCE #MACHINELEARNING
#LONGCONTEXT_

