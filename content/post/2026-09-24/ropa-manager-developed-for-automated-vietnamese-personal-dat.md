---
title: "RoPA Manager Developed for Automated Vietnamese Personal Data Protection Compliance"
slug: "ropa-manager-developed-for-automated-vietnamese-personal-data-protection-compliance"
description: "Researchers have proposed RoPA Manager, a system designed to automate the extraction of information for Records of Processing Activities (RoPA) to help organizations comply with Vietnam's upcoming..."
date: 2026-09-24T18:02:55+05:30
tags: [RoPA, Vietnam, LLM, DataProtection, Compliance]
categories: ["AI", "Artificial Intelligence", "Data Privacy", "Legal Technology"]
author: "Shoubhik Banerjee"
draft: false
---

# RoPA Manager Developed for Automated Vietnamese Personal Data Protection Compliance

Researchers have proposed RoPA Manager, a system designed to automate the extraction of information for Records of Processing Activities (RoPA) to help organizations comply with Vietnam's upcoming data protection laws.

## 💡 Why it matters
Vietnam's Personal Data Protection Law (Law No. 91/2025/QH15) and Decree No. 356/2025/ND-CP, effective January 1, 2026, require organizations to maintain RoPA. Manual preparation is labor-intensive, and the use of cloud-hosted large language models (LLMs) may conflict with data-sovereignty requirements.

## 🧩 How it works
RoPA Manager uses hybrid retrieval and locally deployed LLMs to extract information. The system combines:
* Lexical ranking over tsvector
* Dense-vector search
* Reciprocal Rank Fusion (RRF)

## ⚙️ Key details
To evaluate the system, a Vietnamese RoPA benchmark was introduced containing:
* 32 organizations
* 77 processing activities
* 12 field groups
* 4,338 reference values

Evaluation was conducted at three levels:
* **Automated Scorer:** Achieved F1 = 0.9493 [0.9436, 0.9548] on perturbed data (measuring scorer robustness).
* **End-to-end Extraction:** Achieved token coverage of 50.04-55.25% against reference labels.
* **Expert Review:** Two independent experts reviewed 35.9% of reference values (1,558 values), found no incorrect values, and achieved 99.68% agreement (PABAK = 0.9936).

Value-level precision was not measured.

## 📊 Model Performance
Testing across 32 paired scenarios on a 24 GB GPU compared locally deployed and cloud-based models:

| Model | Deployment | Performance Notes |
| :--- | :--- | :--- |
| Qwen3.5-27B-GPTQ-Int4 | Local | No statistically significant difference from DeepSeek-V4-Flash (0.20 percentage point difference, p = 0.72) |
| DeepSeek-V4-Flash | Cloud | Baseline for comparison |
| Gemma-4-31B | Local | Performed significantly worse (p < 0.01) |

#RoPA #Vietnam #LLM #DataProtection #Compliance

---

*Source: [Automated Extraction of Records of Processing Activities (RoPA) Using Hybrid RAG and Locally Deployed Large Language Models](https://arxiv.org/abs/2609.27359v1)*
