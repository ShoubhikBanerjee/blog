---
title: "GLM-4.5-Air-REAP-82B-A12B: Revolutionary MoE Compression for Efficient AI"
description: "Experience groundbreaking AI model compression with REAP pruning technology that
achieves 25% parameter reduction while maintaining near-identical performance across coding,
reasoning, and function calling tasks."
date: 2025-10-28T01:23:27.105972+05:30
tags: ["GLM-4.5-Air", "REAP", "MoE", "Model-Compression", "Expert-Pruning", "AI-Optimization", "vLLM", "Code-Generation", "Function-Calling", "Mixture-of-Experts"]
categories: ["AI", "Machine Learning", "Model Optimization"]
image: "https://i.imgur.com/rmzG3gg.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 GLM-4.5-Air-REAP-82B-A12B: Revolutionary MoE Compression for Efficient AI

![REAP](https://i.imgur.com/rmzG3gg.png)

*Experience the power of expert pruning with REAP - making AI models lighter without
compromising performance*

## ✨ Highlights

Meet **GLM-4.5-Air-REAP-82B-A12B**, a groundbreaking **memory-efficient compressed variant** of
GLM-4.5-Air that maintains near-identical performance while being **25% lighter**. This
innovative model represents a significant leap forward in AI model optimization.

This cutting-edge model was created using **REAP (Router-weighted Expert Activation Pruning)**,
a revolutionary expert pruning method that selectively removes redundant experts while
preserving the router's independent control over remaining experts. Here's what makes it exceptional:

- **🎯 Near-Lossless Performance**: Maintains almost identical accuracy on code generation,
agentic coding, and function calling tasks compared to the full 106B model
- **💾 25% Memory Reduction**: Compressed from 106B to 82B parameters, significantly lowering
deployment costs and memory requirements
- **🔧 Preserved Capabilities**: Retains all core functionalities including code generation,
agentic workflows, repository-scale understanding, and function calling
- **🔄 Drop-in Compatibility**: Works with vanilla vLLM - no source modifications or custom
patches required
- **⚡ Optimized for Real-World Use**: Particularly effective for resource-constrained
environments, local deployments, and academic research

---

## 📋 Model Overview

**GLM-4.5-Air-REAP-82B-A12B** delivers enterprise-grade performance with the following
specifications:

| **Specification** | **Details** |
| --- | --- |
| **Base Model** | GLM-4.5-Air |
| **Compression Method** | REAP (Router-weighted Expert Activation Pruning) |
| **Compression Ratio** | 25% expert pruning |
| **Type** | Sparse Mixture-of-Experts (SMoE) Causal Language Model |
| **Number of Parameters** | 82B total, 12B activated per token |
| **Number of Layers** | 46 |
| **Number of Attention Heads (GQA)** | 96 for Q and 8 for KV |
| **Number of Experts** | 96 (uniformly pruned from 128) |
| **Number of Activated Experts** | 8 per token |
| **Context Length** | 131,072 tokens |
| **License** | MIT |

---

## 📊 Evaluations

The performance comparison demonstrates the effectiveness of REAP compression:

| **Benchmark** | **GLM-4.5-Air** | **GLM-4.5-Air-REAP-82B-A12B** |
| --- | --- | --- |
| **Compression** | — | 25% |
| **Coding** |  |  |
| **HumanEval** | 92.7 | 89.6 |
| **HumanEval+** | 86.0 | 84.8 |
| **MBPP** | 86.2 | 84.4 |
| **MBPP+** | 69.8 | 69.6 |
| **Reasoning** |  |  |
| **LiveCodeBench** (25.01 - 25.05, thinking) | 39.6 | 42.9 |
| **GPQA diamond** (thinking) | 65.2 | 65.2 |
| **AIME24** (thinking) | 83.3 | 80.0 |
| **MATH-500** (thinking) | 94.8 | 94.8 |
| **Tool Calling** |  |  |
| **BFCL-v3** | 73.4 | 71.8 |
| **BFCL-v3** (thinking) | 76.8 | 76.3 |
| **τ²-bench** (airline) | 63.3 | 64.0 |
| **τ²-bench** (retail) | 72.8 | 75.1 |
| **τ²-bench** (telecom) | 28.4 | 30.7 |
| **τ²-bench** (telecom, thinking) | 27.2 | 26.9 |

🟩 *This checkpoint maintains almost identical performance while being 25% lighter.*

--- 
## 🚀 Deployment

Deploy the model effortlessly using the **latest vLLM** (v0.11.0) with no source modifications
or custom patches required:

```bash
vllm serve cerebras/GLM-4.5-Air-REAP-82B-A12B \ --tensor-parallel-size 4 \
  --tool-call-parser glm45 \ --enable-auto-tool-choice \
  --enable-expert-parallel
```

💡 *Pro tip: If you encounter insufficient memory when running this model, you might need to set
 a lower value for `--max-num-seqs` flag (e.g., set to 64).*

--- 
## 🧩 Model Creation

This checkpoint was created by applying the **REAP (Router-weighted Expert Activation Pruning)**
 method uniformly across all Mixture-of-Experts (MoE) blocks of **GLM-4.5-Air**, with a **25% pruning rate**.

### How REAP Works

REAP introduces a novel approach to expert selection by leveraging a sophisticated **saliency
criterion** that considers both:

- **🎯 Router gate values**: How frequently and strongly the router activates each expert
- **📊 Expert activation norms**: The magnitude of each expert's output contributions

This dual consideration ensures that experts contributing minimally to the layer's output are
pruned, while preserving those that play critical roles in the model's computations.

### Key Advantages

- **⚡ One-Shot Compression**: No fine-tuning required after pruning - the model is immediately
ready for deployment
- **🎛️ Preserved Router Control**: Unlike expert merging methods, REAP maintains the router's
independent, input-dependent control over remaining experts, avoiding "functional subspace collapse"
- **🎨 Generative Task Superiority**: REAP significantly outperforms expert merging approaches
on generative benchmarks (code generation, creative writing, mathematical reasoning) while
maintaining competitive performance on discriminative tasks

### Calibration

The model was calibrated using a diverse mixture of domain-specific datasets including:

- Code generation samples (evol-codealpaca)
- Function calling examples (xlam-function-calling)
- Agentic multi-turn trajectories (SWE-smith-trajectories)

📚 **Additional Resources:**
- 🧾 [arXiv Preprint](https://arxiv.org/abs/2510.13999)
- 🧾 REAP Blog
- 💻 REAP Codebase (GitHub)

--- 
## ⚖️ License

This model is derived from **zai-org/GLM-4.5-Air** and distributed under the **MIT license**.

--- 
## 🧾 Citation

If you use this checkpoint, please cite the REAP paper:

```bibtex
@article{lasby-reap, title={REAP the Experts: Why Pruning Prevails for One-Shot MoE compression},
  author={Lasby, Mike and Lazarevich, Ivan and Sinnadurai, Nish and Lie, Sean and Ioannou, Yani
and Thangarasa, Vithursan}, journal={arXiv preprint arXiv:2510.13999},
  year={2025} }
```

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/cerebras/GLM-4.5-Air-REAP-82B-A12B*

--- 
## 🏁 Conclusion

GLM-4.5-Air-REAP-82B-A12B represents a significant advancement in AI model compression
technology. By achieving a 25% reduction in parameters while maintaining near-identical
performance across critical benchmarks, REAP demonstrates that intelligent expert pruning can
deliver both efficiency and effectiveness. This breakthrough makes high-performance AI more
accessible for resource-constrained environments, local deployments, and academic research,
while opening new possibilities for scalable AI deployment strategies.

--- 
*#AI #MACHINELEARNING #MOE #COMPRESSION #DEEPLEARNING #REAP #GLM #HUGGINGFACE #VLLM #PRUNING*

