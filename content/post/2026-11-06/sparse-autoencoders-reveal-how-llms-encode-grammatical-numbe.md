---
title: "Sparse Autoencoders Reveal How LLMs Encode Grammatical Number"
slug: "sparse-autoencoders-reveal-how-llms-encode-grammatical-number"
description: "Large Language Models (LLMs) can be probed with Sparse Autoencoders (SAEs) to expose how they represent grammatical number. Researchers trained SAEs on a 70‑million‑parameter model (Pythia‑70M) and..."
date: 2026-11-06T22:02:31+05:30
tags: [SparseAutoencoders, GrammaticalNumber, LLMInterpretability]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Interpretability", "Large Language Models"]
author: "Shoubhik Banerjee"
draft: false
---

# Sparse Autoencoders Reveal How LLMs Encode Grammatical Number

Large Language Models (LLMs) can be probed with Sparse Autoencoders (SAEs) to expose how they represent grammatical number. Researchers trained SAEs on a 70‑million‑parameter model (Pythia‑70M) and showed how specific SAE‑derived features drive the model’s choice of plural versus singular verb forms.

## 🔍 Overview
- SAEs translate LLM hidden‑state vectors into a human‑comprehensible list of features or symbols.
- They provide insight into an LLM’s knowledge representation and internal “mental” grammar, which is of pragmatic interest for mechanistic interpretation of AI behavior.

## 🧩 How it works
- An SAE was trained on the hidden states of Pythia‑70M, a model with fewer than 100 M parameters trained on a small corpus.
- The SAE discovered features named “plural noun”, “plural matrix subject”, and “generate a plural verb”.
- By adding or removing these features from the hidden states of tokens, the researchers observed changes in the verb form the model generated.

## ⚙️ Key Findings
- Adding the plural features causes the model to produce plural verbs such as **are**, **do**, or **have** in responses to prompts like “the men in the park”.
- Removing those features from plural‑subject noun tokens makes the model produce singular verbs (**is**, **does**, **has**) instead.
- Corresponding “singular noun” and “generate a singular verb” features are not as effective for forcing singular verb forms.
- This asymmetry suggests that Pythia‑70M uses a **privative representation** of grammatical number in English.
- The same approach replicated on larger models (Gemma‑2‑2b and Llama‑3.1‑8b) yielded similar results.

## 📊 Feature Effect Table
| Feature | Effect on Verb Form |
|---|---|
| plural noun | Promotes plural verb generation |
| plural matrix subject | Promotes plural verb generation |
| generate a plural verb | Promotes plural verb generation |
| singular noun | Less effective at inducing singular verbs |
| generate a singular verb | Less effective at inducing singular verbs |

## 💡 Why it matters
- Shows a concrete mechanism for probing and steering LLM grammar via SAE‑derived features.
- Introduces a novel methodological contribution for mechanistic interpretation of AI behavior.


#SparseAutoencoders #GrammaticalNumber #LLMInterpretability

---

*Source: [Encoding and Propagation of Grammatical Number in Large Language Models](https://arxiv.org/abs/2611.07283v1)*
