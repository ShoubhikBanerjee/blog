---
title: "Correction Audit Protocol Separates Harm from Useful Gain in AI Concept Corrections"
slug: "correction-audit-protocol-separates-harm-from-useful-gain-in-ai-concept-corrections"
description: "Researchers have proposed a correction audit, a reproducible evaluation protocol that disentangles the effects of concept corrections on AI model predictions. The method was tested on breast..."
date: 2026-11-18T18:09:03+05:30
tags: [AIevaluation, conceptcorrection, medicalAI, machinelearning, breastultrasound, CUBdataset]
categories: ["AI", "Machine Learning", "AI Evaluation", "Computer Vision", "Medical AI"]
author: "Shoubhik Banerjee"
draft: false
---

# Correction Audit Protocol Separates Harm from Useful Gain in AI Concept Corrections

Researchers have proposed a correction audit, a reproducible evaluation protocol that disentangles the effects of concept corrections on AI model predictions. The method was tested on breast ultrasound diagnosis and the CUB dataset, revealing that reducing harm alone does not indicate better corrections unless considered alongside useful gain, absolute risk, and the starting prediction.

## 🔍 Overview
- A correction audit evaluates how expert corrections to concept predictions affect model diagnoses.
- The protocol splits each correction into harm and useful gain on identical events.
- It separates the starting prediction from the correction response.
- Objectives are compared using amplitude baselines matched in source harm.

## 🧩 How It Works
- **Separates explanations**: Distinguishes between harm reduction from weaker correction responses versus from better initial predictions.
- **Splits corrections**: Measures harm and useful gain on the same events.
- **Isolates starting prediction**: Evaluates correction response independent of the uncorrected baseline.
- **Uses matched baselines**: Compares objectives against amplitude baselines with equivalent source harm.

## ⚙️ Key Details
### Breast Ultrasound Experiments
- Three breast-ultrasound sources tested with BI-RADS descriptors.
- 21 source comparisons pooled over six seeds.
- Worst-case correction training lowered harm but sacrificed more useful gain in all comparisons.
- Corrected negative log-likelihood (NLL) increased.
- Selecting models by harm alone chose the less helpful model on all three sources.

### CUB Experiments
- Monotonic harm penalty at reported weight tested on 80 concept sets.
- Path-level harm decreased in all 80 concept sets.
- NLL increased in all 80 concept sets.
- NLL increase occurred almost entirely before any correction was applied.
- Rescaling responses to match source harm reproduced penalty's mean harm, useful gain, and NLL within 0.0005 nat margin.

## 💡 Why It Matters
- Lower harm signals better corrections only when interpreted with useful gain, absolute risk, and the starting prediction.
- Harm can decrease artifactually when models respond less to corrections or start from worse uncorrected predictions.
- Model selection based solely on harm metrics picks less helpful models.
- The correction audit provides a reproducible framework to avoid these pitfalls.

#AIevaluation #conceptcorrection #medicalAI #machinelearning #breastultrasound #CUBdataset

---

*Source: [When Lower Harm Misleads: Auditing Concept Corrections](https://arxiv.org/abs/2611.22084v1)*
