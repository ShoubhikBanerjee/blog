---
title: "Introduction of pylazaro for Automatic Extraction of Spanish Lexical Borrowings"
slug: "introduction-of-pylazaro-for-automatic-extraction-of-spanish-lexical-borrowings"
description: "A new open-source Python package called pylazaro has been developed for the automatic extraction of unassimilated lexical borrowings, primarily anglicisms, from Spanish text."
date: 2026-09-25T18:03:21+05:30
tags: [pylazaro, Python, NLP, SpanishLanguage, OpenSource]
categories: ["AI", "Natural Language Processing", "Machine Learning", "Software Development"]
author: "Shoubhik Banerjee"
draft: false
---

# Introduction of pylazaro for Automatic Extraction of Spanish Lexical Borrowings

A new open-source Python package called pylazaro has been developed for the automatic extraction of unassimilated lexical borrowings, primarily anglicisms, from Spanish text.

## 🧩 How it works
pylazaro provides a single interface to five sequence labeling models. These models were trained using different libraries, allowing users to run and switch between them without managing the idiosyncrasies of each individual library.

## 💡 Why it matters
Performance tests show that pylazaro outperforms general-purpose LLMs on this specific task:

| Model Type | F1 Score |
| :--- | :--- |
| General-purpose LLMs | Below 0.40 |
| Best pylazaro model | 0.86 |

## ⚙️ Key details
* The library powers the Observatorio Lazaro, which monitors anglicism usage in the Spanish press.
* The package has been downloaded more than 58,000 times.

## 🚀 Availability
* Installation: Available via PyPI.
* Documentation: Hosted on readthedocs.
* Testing: Accessible through a live demo on HuggingFace Spaces.

#pylazaro #Python #NLP #SpanishLanguage #OpenSource

---

*Source: [pylazaro: a Python package for anglicism extraction in Spanish](https://arxiv.org/abs/2609.29276v1)*
