---
title: "Decision models turn LLMs into structured classifiers"
slug: "decision-models-turn-llms-into-structured-classifiers"
description: "TypeSafe AI introduced Jev, a decision model that treats a large language model as a structured classifier rather than a free‑form generator."
date: 2026-11-10T22:09:41+05:30
tags: [DecisionModels, LLM, ZeroShotClassification]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Applications"]
image: "https://huggingface.co/blog/assets/decision/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Decision models turn LLMs into structured classifiers

TypeSafe AI introduced Jev, a decision model that treats a large language model as a structured classifier rather than a free‑form generator.

## 🔍 Overview
- Large Language Models (LLMs) are exceptionally good at generating text.
- We use them to answer questions, write code, reason about problems, and so much more.
- Decision models shift from token‑by‑token generation to assigning probabilities to answers the application already understands.

## 🧩 How it works
- Fundamental interface: **State + Questions + Allowed Answers → Decisions + Probabilities**.
- A decision model takes some input context (state), evaluates a question with a set of predefined possible answers (primitives), and returns a structured decision along with probabilities.
- Example pipeline call: `decide = pipeline("decision", model="autotrust/GEV-26B-Decide")`.
- Instead of asking a model to generate an answer token by token, we ask it to assign probabilities to the answers that our application already understands.
- Constrained decoding (e.g., using Outlines or XGrammar) can enforce JSON schemas, but it adds computational overhead.

## ⚙️ Key details
- TypeSafe AI introduced Jev, describing it as a **System One** model; the community now uses the term **decision model** to describe this computational role.
- The name draws inspiration from the distinction between fast, intuitive thinking (System 1) and slower, deliberative thinking (System 2).
- Many applications already use language models for classification, routing, and other structured tasks.
- Conventional classifiers have a fixed head: adding a new label (e.g., a fourth department such as Legal) requires modifying the head, collecting data, and retraining.
- Zero‑shot classification addresses this limitation by supplying candidate labels at inference time. Example: `classifier = pipeline("zero-shot-classification", model="facebook/bart-large-mnli")`.

| Pipeline | Model |
|---|---|
| decision | autotrust/GEV-26B-Decide |
| zero-shot-classification | facebook/bart-large-mnli |

## 💡 Why it matters
- When an application only needs to choose between predefined answers, autoregressive decoding can be unnecessary work.
- Because the model selects from allowed answers, it reduces the risk of producing invalid JSON, unexpected keys, or answers outside the allowed choices.
- This approach is useful for routing customer‑support requests—determining which team should handle the request, how urgent it is, and whether the customer is requesting a refund.

![figure](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/decision/decision-models.png)

#DecisionModels #LLM #ZeroShotClassification

---

*Source: [Decision Models in Hugging Face](https://huggingface.co/blog/decision)*
