---
title: "Z.ai releases GLM 5.4 with looped transformer architecture"
slug: "z-ai-releases-glm-5-4-with-looped-transformer-architecture"
description: "Z.ai has launched GLM 5.4, their first model to use a looped transformer architecture. This innovation allows for deeper networks without increasing the parameter count, making it more efficient for..."
date: 2026-11-24T06:12:57+05:30
tags: [AI, MachineLearning, Zai, GLM, LoopedTransformer]
categories: ["AI", "Machine Learning", "AI Models", "Natural Language Processing"]
image: "https://static.simonwillison.net/static/2026/glm-family-4.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Z.ai releases GLM 5.4 with looped transformer architecture

Z.ai has launched GLM 5.4, their first model to use a looped transformer architecture. This innovation allows for deeper networks without increasing the parameter count, making it more efficient for tasks requiring reasoning.

## 🔍 Overview

- GLM 5.4 is a new model from Z.ai, featuring a looped transformer architecture.
- It's designed to be more efficient in tasks requiring reasoning, such as agentic coding.

## 🧩 How it works

- In a standard Transformer, each layer runs once per forward pass.
- In a Loop Transformer, a group of weight-shared layers runs for multiple iterations, refining the hidden states from the previous pass.
- Inkling 2 Mini, a looped transformer, runs the middle layers of the model three times for every token.

## ⚙️ Key details

- GLM 5.4 is not yet available as open weights.
- It can be accessed through the Z.ai API, which requires a Coding Plan subscription.
- The API is OpenAI-compatible and can be accessed at https://api.z.ai/api/v1.

## 🚀 Availability

- GLM 5.4 is currently only accessible through the Z.ai API with a Coding Plan subscription.

## 💡 Why it matters

- The looped transformer architecture allows for more reasoning and can reach the right answer with fewer tokens.
- This makes it particularly useful for tasks such as agentic coding that depend on reasoning quality.

## 📊 Performance

- GLM 5.4's pelicans (a comparison metric) are more comparable to those from OpenAI or Anthropic models than previous generations.
- The style transition between GLM 5.2 and 5.3 is stark, with 5.3 and 5.4 being more similar to OpenAI and Anthropic models.

## 📈 Comparison

| Model | Pelicans Quality | Comparison to OpenAI/Anthropic Models |
|-------|-------------------|-------------------------------------------|
| GLM 5.1 | Different | Radically different |
| GLM 5.2 | Different | Radically different |
| GLM 5.3 | Similar | Much more comparable |
| GLM 5.4 | Similar | Much more comparable |


![figure](https://static.simonwillison.net/static/2026/glm-5.4-max.webp)

#AI #MachineLearning #Zai #GLM #LoopedTransformer

---

*Source: [GLM-5.4: Toward Generalized Coding with Our First Loop Transformer](https://simonwillison.net/2026/Nov/23/glm-54/)*
