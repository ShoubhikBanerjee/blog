---
title: "Concept-Based Framework for Clinical Prediction Without Supervision"
slug: "concept-based-framework-for-clinical-prediction-without-supervision"
description: "A new framework for concept-based interpretation in clinical text prediction was submitted on November 10, 2026. This approach allows for model transparency without the need for expensive annotated..."
date: 2026-11-11T18:02:06+05:30
tags: [C, l, i, n, i, c, a, l, P, r, e, d, i, c, t, i, o, n, C, o, n, c, e, p, t, B, a, s, e, d, I, n, t, e, r, p, r, e, t, a, t, i, o, n, M, a, c, h, i, n, e, L, e, a, r, n, i, n, g, H, e, a, l, t, h, c, a, r, e, A, I, N, L, P]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "N", "a", "t", "u", "r", "a", "l", "L", "a", "n", "g", "u", "a", "g", "e", "P", "r", "o", "c", "e", "s", "s", "i", "n", "g", ",", "H", "e", "a", "l", "t", "h", "c", "a", "r", "e", ",", "C", "o", "m", "p", "u", "t", "a", "t", "i", "o", "n", "a", "l", "L", "i", "n", "g", "u", "i", "s", "t", "i", "c", "s"]
author: "Shoubhik Banerjee"
draft: false
---

# Concept-Based Framework for Clinical Prediction Without Supervision

A new framework for concept-based interpretation in clinical text prediction was submitted on November 10, 2026. This approach allows for model transparency without the need for expensive annotated concept labels.

## 🔍 Overview
Concept-based interpretation explains blackbox models using human-understandable concepts. However, most existing methods require annotated concept labels, which are expensive to obtain in clinical text. This study aims to enable concept-based interpretation for language models without concept supervision on clinical prediction tasks.

## 🧩 How it works
The proposed framework utilizes a tailored cross-attention bottleneck to enable interpretation without supervision.
*   Clinical text and text descriptions of medical concepts are tokenized and embedded by a pretrained language model.
*   A cross-attention module estimates the presence of each concept for each text token.
*   Concept relevance scores are pooled and used in a linear prediction layer.

## ⚙️ Key details
The framework was evaluated across two clinical prediction tasks:

| Task | Dataset |
| :--- | :--- |
| Chest trauma severity stratification | Private |
| In-hospital mortality prediction | MIMIC-III |

*   Performance was measured against blackbox models, achieving AUROC values within 0.02 of the corresponding blackbox models.
*   The framework supports cohort- and patient-level interpretation.

## 💡 Why it matters
This framework realizes concept-based interpretation without requiring ground-truth concept presence labels. It improves the transparency of clinical text predictions while maintaining strong performance in clinical prediction tasks.

#C #l #i #n #i #c #a #l #P #r #e #d #i #c #t #i #o #n #, # #C #o #n #c #e #p #t #B #a #s #e #d #I #n #t #e #r #p #r #e #t #a #t #i #o #n #, # #M #a #c #h #i #n #e #L #e #a #r #n #i #n #g #, # #H #e #a #l #t #h #c #a #r #e #A #I #, # #N #L #P

---

*Source: [A Concept-Based Interpretable Framework for Clinical Text-based Prediction via Token-Concept Attention without Concept Supervision](https://arxiv.org/abs/2611.13564v1)*
