---
title: "Stanford releases DSPy: Declarative Python framework for programming language models"
slug: "stanford-releases-dspy-declarative-python-framework-for-programming-language-models"
description: "The Stanford NLP group announced DSPy, a new Python framework that lets developers program language models directly rather than rely on brittle prompts."
date: 2026-11-18T22:09:17+05:30
tags: [DSPy, LanguageModels, AIFramework]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Software Development"]
image: "https://avatars.githubusercontent.com/u/3046006?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Stanford releases DSPy: Declarative Python framework for programming language models

The Stanford NLP group announced DSPy, a new Python framework that lets developers program language models directly rather than rely on brittle prompts.

## 🔍 Overview
- DSPy is the framework for programming—rather than prompting—language models.
- DSPy stands for Declarative Self-improving Python.

## 🧩 How it works
- Instead of brittle prompts, you write compositional Python code and use DSPy to teach your LM to deliver high-quality outputs.
- It lets you iterate fast on building modular AI systems and provides algorithms for optimizing prompts and weights, suitable for simple classifiers, sophisticated RAG pipelines, or Agent loops.

## ⚙️ Key details
- The current LM integration uses bundled native lm15 engines, without a LiteLLM runtime dependency or fallback.
- See the LM migration guide for breaking changes to provider options, custom LMs, text completions, and embeddings.

## 📚 Research timeline
| Date | Title |
|------|-------|
| Jul'25 | GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning |
| Jun'24 | Optimizing Instructions and Demonstrations for Multi-Stage Language Model Programs |
| Oct'23 | DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines |
| Jul'24 | Fine-Tuning and Prompt Optimization: Two Great Steps that Work Better Together |
| Jun'24 | Prompts as Auto-Optimized Training Hyperparameters |
| Feb'24 | Assisting in Writing Wikipedia-like Articles From Scratch with Large Language Models |
| Jan'24 | In-Context Learning for Extreme Multi-Label Classification |
| Dec'23 | DSPy Assertions: Computational Constraints for Self-Refining Language Model Pipelines |
| Dec'22 | Demonstrate-Search-Predict: Composing Retrieval & Language Models for Knowledge-Intensive NLP |

## 🚀 Availability
- Install via pip: `pip install dspy`
- Install latest from source: `pip install git+https://github.com/stanfordnlp/dspy.git`

## 🎨 Branding
- The DSPy logo is designed by Chuyi Zhang.

#DSPy #LanguageModels #AIFramework

---

*Source: [stanfordnlp/dspy](https://github.com/stanfordnlp/dspy)*
