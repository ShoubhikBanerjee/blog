---
title: "ProMediConv Benchmarking Framework and Dataset for Mediation Dialogues"
slug: "promediconv-benchmarking-framework-and-dataset-for-mediation-dialogues"
description: "A new benchmarking framework called ProMediConv has been introduced to evaluate mediation‑oriented dialogue models."
date: 2026-09-11T22:04:55+05:30
tags: [MediationAI, Benchmarking, DialogueSystems, Dataset]
categories: ["AI", "Artificial Intelligence", "Natural Language Processing", "Dialogue Systems"]
author: "Shoubhik Banerjee"
draft: false
---

# ProMediConv Benchmarking Framework and Dataset for Mediation Dialogues

A new benchmarking framework called ProMediConv has been introduced to evaluate mediation‑oriented dialogue models.

## 🔍 Overview
- ProMediConv models mediation as a proactive, multi‑stage, party‑aware dialogue process.
- It incorporates 11 mediation strategies and four party‑behavior (BP) states.

## 🧩 How it works
- The framework treats each conversation as a sequence of stages where parties can adopt different behavior patterns.
- Utterance‑level annotations capture both the strategy employed and the current BP state.

## ⚙️ Key details
- Dataset: 972 complete real‑world mediation cases with strategy and BP annotations.
- Metric: MAD (Mean Attribute Difference) measures BP shifts across the dialogue.
- Baseline: ProMediAgent is the tailored baseline evaluated alongside diverse models.

| Component | Description |
|---|---|
| ProMediConv | Benchmarking framework that models mediation as proactive, multi‑stage, party‑aware dialogue, incorporating 11 strategies and four BP states |
| MAD (Mean Attribute Difference) | Fine‑grained metric that captures party‑behavior shifts throughout the dialogue |
| ProMediAgent | Tailored baseline evaluated in the comprehensive benchmark |

## 🚀 Availability
- The dataset and codebase are accessible at this https URL.


#MediationAI #Benchmarking #DialogueSystems #Dataset

---

*Source: [ProMediConv: Benchmarking Proactive Conversational Agents in Legal Dispute Mediation](https://arxiv.org/abs/2609.11101v1)*
