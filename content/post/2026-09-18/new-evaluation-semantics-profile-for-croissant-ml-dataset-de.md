---
title: "New Evaluation Semantics Profile for Croissant ML Dataset Descriptors"
slug: "new-evaluation-semantics-profile-for-croissant-ml-dataset-descriptors"
description: "A new additive profile has been developed to provide evaluation semantics for Croissant, the de facto machine-readable descriptor for ML datasets."
date: 2026-09-18T18:02:43+05:30
tags: [Croissant, MLdatasets, DataGovernance, ODRL]
categories: ["AI", "Machine Learning", "Data Management", "Technical Standards"]
author: "Shoubhik Banerjee"
draft: false
---

# New Evaluation Semantics Profile for Croissant ML Dataset Descriptors

A new additive profile has been developed to provide evaluation semantics for Croissant, the de facto machine-readable descriptor for ML datasets.

## 🔍 Overview
While Croissant version 1.1 carries data use conditions—recommending ODRL and DUO—it does not specify how these are evaluated. It lacks a decision procedure, bounds on evaluation cost, outcomes for conditions an implementation cannot evaluate, records of what was checked, and information on composition with caller-side authority.

## 🧩 How it works
An additive profile allows a dataset to declare admitted operations and the conditions for those admissions. Key technical features include:

* **Closed Operator Set**: Uses a closed set of five operators with a full decision procedure.
* **Automated Gating**: A gate can decide based on the descriptor alone and record the checks performed.
* **State Space Separation**: Caller-bound and data-bound policies range over non-overlapping state spaces, meaning neither permit set contains the other.

## ⚙️ Key details
Testing was conducted using two corpora with evidence kept apart, as well as a corpus generated from the profile's grammar to cover every conformance clause, refusal class, and operator.

**Deployment Results (nf-core pipeline)**

| Metric | Result |
| :--- | :--- |
| Decision Accuracy | Profile document decisions match the gate's native descriptor record for record |
| Compatibility | Stripping the layer leaves a valid Croissant document |
| Performance Cost | 11.7 $\mu$s added cost against a 119 $\mu$s decision |

Additionally, across valid cases, 552 complete decision records showed agreement between the native descriptor, profile terms, and the ODRL policy in usageInfo.

#Croissant #MLdatasets #DataGovernance #ODRL

---

*Source: [A Policy Profile for Croissant: Refusal as a Property of the Dataset](https://arxiv.org/abs/2609.19640v1)*
