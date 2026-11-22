---
title: "DeepFabric generates synthetic data for language model training"
slug: "deepfabric-generates-synthetic-data-for-language-model-training"
description: "DeepFabric is a tool designed to generate synthetic training data for language models and agent evaluations. It combines reasoning traces with tool-calling patterns to create high-quality,..."
date: 2026-11-22T18:07:49+05:30
tags: [DeepFabric, SyntheticData, LLMTraining, AgentEvaluations, MCP, HuggingFace]
categories: ["AI", "Machine Learning", "AI Agents", "Data Engineering", "LLM Development"]
image: "https://avatars.githubusercontent.com/u/289819636?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# DeepFabric generates synthetic data for language model training

DeepFabric is a tool designed to generate synthetic training data for language models and agent evaluations. It combines reasoning traces with tool-calling patterns to create high-quality, domain-specific datasets that teach models to think, plan, and act effectively, call tools correctly, and conform to strict schema structures.

## 🔍 Overview
The system distinguishes itself through unique topic graph generation algorithms that ensure high diversity while maintaining domain-anchored relevance. This approach guides sample creation to cover all necessary subtopics while avoiding redundancy, a common issue in other tools that can lead to model overfitting.

## 🧩 How it works
* **Data Generation:** The process involves constrained decoding and response validation.
* **Tool Execution:** Real tool executions occur within isolated webassembly environments.
* **Accuracy:** These mechanisms ensure generated samples strictly adhere to structured schemas, variable constraints, and execution correctness, providing exact syntax and structure for training pipelines.
* **Tool Definitions:** Tool definitions can be imported directly from MCP (Model Context Protocol) server schemas, automatically mocked, or based on real-life interfaces.
* **Standard Tools:** A standard set of common tools, such as `list_files()` and `read_file()`, is included.

## ⚙️ Key details
* **Deployment Options:** DeepFabric can be used as a library, a CLI tool, or via YAML configuration.
* **Configuration:** The YAML configuration includes three main sections and optional shared LLM defaults.
* **Mocked Execution:** Using mocked tool execution requires a running Spin service, which is provided in a Docker image.
* **Example Output:** A specific configuration generated a topic graph with 27 unique nodes, resulting in 27 training samples saved to `dataset.jsonl` and achieving 100% topic coverage.

## 🚀 Availability
* **Integration:** Generated datasets can be automatically uploaded to Hugging Face.
* **Training Frameworks:** Data can be directly imported into popular training frameworks, including TRL, Unsloth, and Axolotl.
* **Evaluation:** A built-in evaluation engine assesses model performance on unseen tasks derived from training splits, covering evaluation-only questions, answers, and tool traces.

#DeepFabric #SyntheticData #LLMTraining #AgentEvaluations #MCP #HuggingFace

---

*Source: [nolabs-ai/deepfabric](https://github.com/nolabs-ai/deepfabric)*
