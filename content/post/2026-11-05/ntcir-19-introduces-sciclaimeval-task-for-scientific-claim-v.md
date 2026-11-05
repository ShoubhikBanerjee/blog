---
title: "NTCIR‑19 Introduces SciClaimEval Task for Scientific Claim Verification"
slug: "ntcir19-introduces-sciclaimeval-task-for-scientific-claim-verification"
description: "A new pilot task, **SciClaimEval**, was launched at NTCIR‑19 to assess how well AI systems can verify scientific claims using the tables and figures from the papers where the claims appear."
date: 2026-11-05T22:04:09+05:30
tags: [SciClaimEval, NTCIR19, MultimodalLLM, ClaimVerification]
categories: ["AI", "Natural Language Processing", "Machine Learning", "Information Retrieval"]
author: "Shoubhik Banerjee"
draft: false
---

# NTCIR‑19 Introduces SciClaimEval Task for Scientific Claim Verification

A new pilot task, **SciClaimEval**, was launched at NTCIR‑19 to assess how well AI systems can verify scientific claims using the tables and figures from the papers where the claims appear.

## 🔍 Overview
- SciClaimEval is a pilot task at NTCIR‑19 focused on verifying scientific claims against the tables and figures of the originating papers.
- The dataset pairs authentic claims from **180 papers** in **machine learning, natural language processing, and medicine** with **contrastive versions** of their tables/figures: one that supports the claim and one that has been minimally altered so it does not.

## 🧩 Task Structure
- **Subtask 1:** Decide whether a given piece of evidence supports a claim.
- **Subtask 2:** Choose which of the two contrastive evidence versions (supporting vs. non‑supporting) matches the claim.

## ⚙️ Participation & Systems
- **22 teams** registered – the highest participation among NTCIR‑19 tasks.
- **14 teams** submitted a total of **177 runs**.
- Most systems relied on **multimodal large language models**, using **prompting and multi‑stage inference** rather than task‑specific fine‑tuning.
- **Open‑weight models**, when placed in carefully designed pipelines, performed on par with proprietary models.

## 📈 Results
- On Subtask 1, the best systems achieved **98.1 % pair accuracy**.
- All six top‑ranked systems depended on the contrastive pairs; the best system that evaluated each claim‑evidence pair in isolation scored **24.3 points lower**.
- **Verifying a single claim against its evidence**, the scenario most relevant in practice, **remains an open problem**.

## 💡 Why it Matters
- Accurate claim verification can help researchers quickly assess the reliability of findings across disciplines.
- The strong performance of multimodal LLMs and open‑weight models highlights the growing capability of accessible AI tools, while the remaining gap underscores the need for further research on direct claim‑evidence reasoning.


#SciClaimEval #NTCIR19 #MultimodalLLM #ClaimVerification

---

*Source: [Overview of the NTCIR-19 SciClaimEval Task: Cross-modal Claim Verification in Scientific Papers](https://arxiv.org/abs/2611.06090v1)*
