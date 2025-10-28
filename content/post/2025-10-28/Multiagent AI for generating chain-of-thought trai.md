---
title: "Multiagent AI for Generating Chain-of-Thought Training Data"
description: "Amazon's innovative multiagent deliberation framework leverages AI agent ensembles
 to autonomously generate high-quality chain-of-thought training data, achieving 29% performance
 improvements and 96% safety enhancements while eliminating expensive human annotation
requirements."
date: 2025-10-28T01:01:14.455684+05:30
tags: ["AI", "Machine Learning", "Chain-of-Thought", "Multiagent Systems", "Responsible AI", "Amazon", "Training Data", "LLM", "Safety", "CoT"]
categories: ["Artificial Intelligence", "Machine Learning", "AI Safety"]
image: "https://assets.amazon.science/dims4/default/1a983f5/2147483647/strip/true/crop/2794x912+0+0/resize/1200x392!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2F4b%2F77%2Fa68e570743c9a8ade1a47b45be41%2Fmultiagent-deliberation-framework.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🤖 Multiagent AI for Generating Chain-of-Thought Training Data

![Multiagent AI Framework](https://assets.amazon.science/dims4/default/1a983f5/2147483647/strip/true/crop/2794x9
12+0+0/resize/1200x392!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2
Fscience%2F4b%2F77%2Fa68e570743c9a8ade1a47b45be41%2Fmultiagent-deliberation-framework.png)

*A schematic of the multiagent-deliberation framework for generating safety-embedded CoTs*

## 🎯 Overview

Chain-of-thought reasoning has emerged as a powerful technique for improving large language
models' (LLMs) reasoning capabilities. By requiring models to not only perform multistep actions
 but also explain their reasoning, this approach significantly enhances AI performance. However,
 generating high-quality chain-of-thought (CoT) training data traditionally requires expensive human annotation.

Amazon's Artificial General Intelligence organization has developed an innovative solution using
 **ensembles of AI agents** to generate high-quality CoT data autonomously. This
multiagent-deliberation approach achieves remarkable improvements in AI safety and performance
across multiple benchmarks.

## 🚀 The Multiagent Deliberation Framework

The research introduces a three-stage framework that leverages multiple LLMs working in concert:

### 1. Intent Decomposition ⚡
An LLM analyzes the user query to identify both explicit and implicit user intents. These
insights, combined with the original query, are then passed to another LLM that generates an initial chain of thought.

### 2. Deliberation 🔄
This iterative process involves multiple AI agents expanding the CoT in sequential fashion while
 factoring in defined policy sets. Each agent reviews and corrects the previous version or
confirms its adequacy. The process continues until an agent determines completeness or exhausts
the predefined deliberation budget.

### 3. Refinement ✨
A final LLM processes the deliberation outputs, filtering out redundant, deceptive, and
policy-inconsistent thoughts to produce clean, coherent reasoning chains.

## 📊 Impressive Performance Results

The research team evaluated their approach using two different LLMs (Qwen and Mixtral) across
five datasets, comparing against baseline pretrained models and conventionally fine-tuned variants.

### Key Performance Metrics

| Metric | LLM_ZS | AIDSAFE | Improvement |
|--------|--------|---------|-------------|
| **Relevance** | 4.66 | **4.68** | 0.43% |
| **Coherence** | 4.93 | **4.96** | 0.61% |
| **Completeness** | 4.86 | **4.92** | 1.23% |
| **CoTs' Faithfulness (Policy)** | 3.85 | **4.27** | 10.91% |
| **Response Faithfulness (Policy)** | 4.85 | **4.91** | 1.24% |
| **Response Faithfulness (CoT)** | 4.99 | **5.00** | 0.20% |

*Auto-grader scores on generated-CoT datasets (1-5 scale)*

### Safety Performance Improvements

**Mixtral Model Results:**

| Evaluation | Dimension | Metric | Dataset | Base | SFT_OG | **SFT_DB (Ours)** |
|------------|-----------|---------|---------|------|--------|------------------|
| Safety | Safe response rate | % | Beavertails | 76 | 79.57 | **96** |
| | | | WildChat | 31 | 33.5 | **85.95** |
| Overrefusal | 1-Overrefuse rate | % | XSTest | **98.8** | 87.6 | 91.84 |
| Utility | Answer accuracy | % | MMLU | **35.42** | 31.38 | 34.51 |
| Jailbreak Robustness | Safe response rate | % | StrongREJECT | 51.09 | 67.01 | **94.04** |

**Qwen Model Results:**

| Evaluation | Dimension | Metric | Dataset | Base | SFT_OG | **SFT_DB (Ours)** |
|------------|-----------|---------|---------|------|--------|------------------|
| Safety | Safe response rate | % | Beavertails | 94.14 | 87.95 | **97** |
| | | | WildChat | 95.5 | 59.42 | **96.5** |
| Overrefusal | 1-Overrefuse rate | % | XSTest | **99.2** | 98 | 93.6 |
| Utility | Answer accuracy | % | MMLU | **75.78** | 55.73 | 60.52 |
| Jailbreak Robustness | Safe response rate | % | StrongREJECT | 72.84 | 59.48 | **95.39** |

## 💡 Key Advantages

### Significant Safety Improvements
- **96% relative increase** in average safety for non-safety trained models (Mixtral)
- **73% improvement** over conventionally fine-tuned models
- **12% and 44% improvements** respectively for safety-trained models (Qwen)

### Cost-Effective Training Data Generation
- Eliminates expensive human annotation requirements
- Automated generation of high-quality CoT training data
- Scalable approach suitable for large-scale applications

### Enhanced Policy Adherence
- **10.91% improvement** in CoT policy faithfulness
- Better alignment with responsible AI principles
- Robust jailbreak resistance across multiple attack vectors

## 🧪 Evaluation Methodology

The research team employed comprehensive evaluation criteria:

### Quality Assessment (1-5 scale):
- **Relevance**: How well the CoT addresses the query
- **Coherence**: Logical consistency of reasoning steps
- **Completeness**: Thoroughness of the reasoning process

### Faithfulness Evaluation:
- Policy-to-CoT alignment
- Policy-to-response consistency
- CoT-to-final-response fidelity

### Benchmark Testing:
- **Beavertails**: Safety evaluation
- **WildChat**: Real-world conversation scenarios
- **XSTest**: Overrefusal detection
- **MMLU**: General utility assessment
- **StrongREJECT**: Jailbreak robustness testing

## 🔮 Future Implications

This research demonstrates the potential for **agentic AI systems** to collaborate in generating
 high-quality training data, reducing dependence on human annotation while improving model
safety and performance. The approach shows particular promise for:

- **Responsible AI Development**: Enhanced policy adherence without sacrificing utility
- **Scalable Training Pipelines**: Automated generation of specialized training datasets
- **Multi-modal Applications**: Potential extension to vision-language models and other domains

## 🙌 Credits

*Originally posted at:
https://www.amazon.science/blog/multiagent-ai-for-generating-chain-of-thought-training-data*

## ✅ Final Thoughts

The multiagent deliberation framework represents a significant advancement in automated training
 data generation for AI systems. By achieving an average 29% improvement across benchmarks while
 dramatically enhancing safety metrics, this approach offers a practical solution to one of
machine learning's most persistent challenges: generating high-quality, policy-compliant training data at scale.

The research not only demonstrates technical innovation but also provides a pathway toward more
responsible AI development, where safety and utility can be enhanced simultaneously through collaborative AI agents.

--- 
*#AI #MACHINELEARNING #CHAINOFTHOUGHT #RESPONSIBLEAI #MULTIAGENT #AMAZON #ACL2025*

