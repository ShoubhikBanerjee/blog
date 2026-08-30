---
title: "Tencent unveils Hy4 Preview, a 770B open‑weight text‑only LLM"
description: "On 29 August 2026, Tencent released **Hy4 Preview**, a new open‑weight text‑only large language model."
date: 2026-08-30T23:12:46+05:30
tags: [Tencent, Hy4, LLM, OpenWeight, ChatTemplate]
categories: [AI]
image: "https://static.simonwillison.net/static/2026-08-29/IMG_7725.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# Tencent unveils Hy4 Preview, a 770B open‑weight text‑only LLM

On 29 August 2026, Tencent released **Hy4 Preview**, a new open‑weight text‑only large language model.

## 🔍 Overview
- Hy4 is a text‑input (no vision) LLM.
- It represents a major size increase over the previous Hy3 model released in July.

## ⚙️ Key specifications
- **Total parameters:** 770 B
- **Active parameters:** 49 B
- **Context window:** 1 M tokens
- **Model size on Hugging Face:** 1.56 TB

### Comparison with Hy3
| Model | Total parameters | Active parameters | Context window | Size on Hugging Face |
|-------|------------------|-------------------|----------------|----------------------|
| Hy4   | 770 B            | 49 B              | 1 M tokens     | 1.56 TB              |
| Hy3   | 295 B            | 21 B              | 256 k tokens   | 598 GB               |

## 🧩 Reasoning control
The `chat_template.jinja` on Hugging Face defines a `reasoning_effort` variable:
- If not defined, it defaults to **"high"**.
- Allowed values are **"high"** and **"no_think"**.
- Providing any other value raises an exception, e.g.,
  `reasoning_effort error : <value>, should be no_think/high`.

## 🚀 Sample behavior
Using the default **high** reasoning level via OpenRouter, a prompt to *"Generate an SVG of a pelican riding a bicycle"* produced the following reasoning trace (excerpt):
```
[...] Let's maybe add a helmet? It could improve riding theme, but may obscure head. Maybe a small cycling cap or helmet? The user didn't ask; can add red helmet? Might be cute. But pelican with big beak; a helmet might obscure. Better maybe no.
Maybe add sunglasses? no.
Maybe add water? no.
```
The trace shows truncated English, suggesting the model favors token efficiency for hidden reasoning text.

## 📦 Availability
Hy4 Preview is hosted on Hugging Face with a download size of **1.56 TB**.


#Tencent #Hy4 #LLM #OpenWeight #ChatTemplate

---

*Source: [Introducing Hy4 Preview](https://simonwillison.net/2026/Aug/29/hy4/)*
