---
title: "LLMON markup language and preview models released for Granite 4.1"
slug: "llmon-markup-language-and-preview-models-released-for-granite-4-1"
description: "A new LLM‑native markup language called **LLMON** (pronounced “lemon”) has been released, together with two experimental preview models built on the Granite 4.1 base."
date: 2026-11-13T12:01:52+05:30
tags: [LLMON, Granite, PromptSecurity, AIModels]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Safety", "AI Infrastructure"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6484ca4d5ff9a3d2ee52a83b/6KFZDHIJkxpICiErHLqAw.gif"
author: "Shoubhik Banerjee"
draft: false
---

# LLMON markup language and preview models released for Granite 4.1

A new LLM‑native markup language called **LLMON** (pronounced “lemon”) has been released, together with two experimental preview models built on the Granite 4.1 base.

## 🔍 Overview
LLMON (LLM Object Notation) is an XML‑like markup designed for causal language models. It separates structure from content by using reserved special‑token delimiters, allowing models to understand explicit tags, unique IDs, and instruction/data boundaries.

## 🧩 How it works
- **Tagging** – Semantically coherent components are wrapped in meaningful tags that start each span.  Boundaries between spans are explicit.
- **Unique IDs** – IDs let the model point to specific instructions anywhere in the context and bind them to the appropriate data payloads.
- **Nested structures** – Declared locally, so the model does not need to track hierarchy over long spans.
- **Vocabulary split** – Structural delimiters are special tokens, leaving the regular vocabulary for content.
- **Chat integration** – The preview models ship with a chat template that works like any other chat model.  A turn can name its parts and mark each part `exec: True` or `exec: False`.  Parts marked `True` are collected into an `exec` block that specifies which instruction to run and on what data.

## ⚙️ Key details
- **Models**

| Model | Parameter Size | Base Model |
|-------|----------------|------------|
| granite-4.1-3b-LLMON-preview | 3 B | Granite 4.1 |
| granite-4.1-8b-LLMON-preview | 8 B | Granite 4.1 |

- **Security** – Indirect prompt injections hidden in user data are mostly ignored because instruction and data are explicitly separated.  In benchmark attacks, success rates drop to nearly zero, whereas regular instruction‑tuned models are hijacked with high probability.
- **Capability** – General capability remains on par with Granite 4.1 Instruct models.
- **Extensibility** – Users can define custom structures and tags, then fine‑tune a LoRA on top of the LLMON models to recognize them.

## 🚀 Availability
- Two preview models are released: `granite-4.1-3b-LLMON-preview` and `granite-4.1-8b-LLMON-preview`.
- A GitHub repository provides a toolkit, example workflows, and templates for working with LLMON.
- Converters are supplied to transform existing JSON into LLMON without loss, and notebooks demonstrate lossless round‑trip conversion.
- Mellea offers native LLMON support by automatically "LLMONizing" its LLM calls.

## 💡 Why it matters
LLMON offers a structured way for prompts to convey semantics to language models, reducing the attack surface for prompt injection while preserving the models' overall performance.  By keeping JSON‑based pipelines and providing conversion tools, teams can adopt LLMON without rewriting existing data processing code.

![figure](https://cdn-uploads.huggingface.co/production/uploads/6484ca4d5ff9a3d2ee52a83b/3UqXuyb58P8n3NiHnJiK4.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6484ca4d5ff9a3d2ee52a83b/VMIEO4qYlmxLhK0DmMO6C.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6484ca4d5ff9a3d2ee52a83b/nv3yYV9JSHPrHEJYfKiqo.gif)

#LLMON #Granite #PromptSecurity #AIModels

---

*Source: [LLMON: An LLM-Native Markup Language, now in Granite 4.1 3B and 8B](https://huggingface.co/blog/ibm-granite/llmon-an-llm-native-markup-language-now-in-granite)*
