---
title: "Researchers Introduce CARing Framework to Improve LLM Next-Visit Diagnosis Prediction"
slug: "researchers-introduce-caring-framework-to-improve-llm-next-visit-diagnosis-prediction"
description: "Researchers have developed CARing, a new framework designed to enhance next-visit diagnosis prediction in large language models (LLMs) by addressing multi-label coverage and tokenization challenges."
date: 2026-10-09T22:05:01+05:30
tags: [ClinicalAI, LLMs, Healthcare]
categories: ["AI", "Machine Learning", "Healthcare Technology", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# Researchers Introduce CARing Framework to Improve LLM Next-Visit Diagnosis Prediction

Researchers have developed CARing, a new framework designed to enhance next-visit diagnosis prediction in large language models (LLMs) by addressing multi-label coverage and tokenization challenges.

## 🔍 Overview

Large language models offer promising potential for next-visit diagnosis prediction due to their capacity to integrate and reason over longitudinal clinical evidence in natural language. However, conventional reinforcement learning for LLM reasoning typically rewards each trajectory based solely on the correctness of its final answer. 

In next-visit diagnosis prediction, multiple diagnoses can be valid at the same time. Independently rewarding a single diagnosis per trajectory does not distinguish repeated hits from the coverage of different diagnoses, which can cause the model's policy to concentrate on only a few correct diagnoses while leaving others uncovered. Furthermore, standard LLM tokenizers can split ICD codes into multiple generic tokens with limited clinical meaning, which requires multiple decoding steps to predict each diagnosis and hinders reasoning over large disease vocabularies.

## 🧩 How it works

To resolve these issues, the CARing framework introduces several technical approaches:

* **Compositional Semantic IDs (SIDs):** Diagnoses are represented with compact SIDs, which encode ontology-enriched disease semantics through residual quantization.
* **Contextual Grounding:** The resulting SID tokens are grounded in natural language and longitudinal electronic health record (EHR) contexts using multi-task alignment and reasoning-enriched training to unlock transferable LLM reasoning.
* **Coverage Reward and Supervision:** Unordered multi-label prediction is improved through a coverage reward for reinforcement learning combined with multi-positive supervision.
* **Inference Flexibility:** At inference time, the model supports both efficient direct constrained decoding and multi-chain reasoning with rank fusion.

## ⚙️ Key details

The CARing framework was evaluated on the MIMIC-III and MIMIC-IV datasets, demonstrating the following performance results:

* It exceeded all EHR-trained baselines in weighted F1.
* It achieved the highest top-k recall at every reported cutoff.
* In reasoning mode, it attained a Recall@30 (R@30) of 46.04% and 46.52%.

## 🚀 Availability

The codes and logs for the CARing framework are available online at the project's repository URL.

#ClinicalAI #LLMs #Healthcare

---

*Source: [Coverage-Aware Reasoning with Medical Tokens for Diagnosis Prediction](https://arxiv.org/abs/2610.10641v1)*
*Source: [Clinician use of language models diverges from how the models are evaluated](https://arxiv.org/abs/2610.11069v1)*
