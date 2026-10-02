---
title: "Adjudicated Query pattern lets AI‑assisted lease compliance stay auditable"
slug: "adjudicated-query-pattern-lets-aiassisted-lease-compliance-stay-auditable"
description: "A new design pattern called Adjudicated Query combines generative AI in Amazon Quick with a deterministic rules engine to let business users ask compliance questions at lease‑scale while keeping the..."
date: 2026-10-02T22:04:29+05:30
tags: [AWS, AI, Compliance, GenerativeAI, AdjudicatedQuery]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Compliance Technology", "Software Architecture"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/30/ML-21832-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Adjudicated Query pattern lets AI‑assisted lease compliance stay auditable

A new design pattern called Adjudicated Query combines generative AI in Amazon Quick with a deterministic rules engine to let business users ask compliance questions at lease‑scale while keeping the final decisions fully auditable.

## 🔍 Overview
- Tens of thousands of apartment leases must be checked against constantly changing state landlord‑tenant laws; manual review only works at small volume.
- Traditional software yields a number that cannot be independently verified.
- Retrieval‑augmented generation, similarity search, and text‑to‑SQL each have gaps (no exhaustive threshold, unknown exclusions, hallucinated predicates).

## 🧩 How it works
- A bounded conversational layer (the model) sits on top of a deterministic rules engine.
- The model performs exactly two actions:
  1. Translate a natural‑language question into a call on a fixed set of typed operations.
  2. Narrate the result that comes back.
- The model never writes a query, never fixes the population, and never makes a determination.
- The rules engine:
  - Stores rules as versioned data, not code.
  - Knows generic comparison operators (gte, lte, equals, exists) and contains no branch naming a jurisdiction or topic.
  - A law change is a rulebook row edit, not a code deployment.
- Every compliance sweep produces a completeness receipt where **compliant + in‑breach + ambiguous + unreadable = scanned**; the run fails if the invariant cannot be satisfied, ensuring no record is silently skipped.

## ⚙️ Key details
- Example scale: a portfolio operator holds 50,000 leases across multiple states.
- Business users ask questions through a chat interface in Amazon Quick.
- The full result set (potentially tens of thousands of rows) lives on a dashboard surface that reads the same data store and is drillable per record.
- The conversational surface displays counts, the receipt, and a labeled sample.
- The pattern applies to other high‑stakes compliance domains such as sanctions screening, insurance claims adjudication, and export control.

## 🚀 Availability
- AWS provides a reference architecture that implements the Adjudicated Query pattern.
- A working sample can be deployed end‑to‑end.

## 💡 Why it matters
- Enables compliance teams to scale beyond the point where manual review is feasible.
- Retains auditability and trust because the deterministic engine, not the language model, makes the pass/fail decision.
- Guarantees that every lease record is accounted for, preventing silent omissions that can occur with similarity search or hallucinated SQL predicates.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/30/ML-21832-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/30/ML-21832-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/30/ML-21832-3.png)

#AWS #AI #Compliance #GenerativeAI #AdjudicatedQuery

---

*Source: [Sweep thousands of leases for compliance using Amazon Quick and the Adjudicated Query pattern | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/sweep-thousands-of-leases-for-compliance-using-amazon-quick-and-the-adjudicated-query-pattern/)*
