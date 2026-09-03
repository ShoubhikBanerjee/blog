---
title: "ClaimReceipt: A New Standard for Verifying AI Agent Claims"
description: "A new specification called ClaimReceipt introduces a rigorous method for verifying claims made by AI agents by binding evidence to a signed experiment manifest."
date: 2026-09-03T18:04:33+05:30
tags: [AIAgents, ModelVerification, Auditing, Transparency]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# ClaimReceipt: A New Standard for Verifying AI Agent Claims

A new specification called ClaimReceipt introduces a rigorous method for verifying claims made by AI agents by binding evidence to a signed experiment manifest.

## 🔍 Overview
Agent evaluations face two key questions: whether a claim can be recomputed from the evidence (sufficiency), and whether the evidence covers the full set of committed experiments (coverage). Generic logs and transcripts are insufficient to answer these reliably.

## 🧩 How it works
ClaimReceipt is a claim-relative receipt specification and selective verifier. For a given claim, it binds typed transaction evidence to a signed experiment manifest and returns one of three results:
- PASS
- INVALID
- INCONCLUSIVE

Verification requires both claim-sufficient evidence and a committed universe against which omissions become visible.

## ⚙️ Key details
- The specification was frozen before implementation (SHA-256 18d109...b81).
- A CR-2 verifier was tested on 1,392 historical buyer-seller records, reproducing all five manually labeled audit verdicts.
- It exactly replays 600 deterministic and 792 post-generation records.
- The system makes every one of 13 declared field groups non-redundant under tested ablations.
- It returns the expected result on 11/11 semantic faults with 0/8 false positives.
- Receipt instrumentation adds 0.021% of model-inference time and 9.9 KB per transaction.

A separate prospective CR-3 epoch run committed 30 assignments before inference. Terminal receipts are signed and chained. Private evidence can be encrypted for an auditor. In tests, complete evidence yielded a coverage and accounting PASS. Withholding one terminal receipt returned INCONCLUSIVE_COVERAGE. Withholding all private openings preserved coverage and protocol verification but made economic claims inconclusive.

A specification-legibility probe indicated that the frozen specification is not yet unambiguous to an independent reader.

#AIAgents #ModelVerification #Auditing #Transparency

---

*Source: [ClaimReceipt: Verifying Evidence Sufficiency and Coverage in Agent Evaluations](https://arxiv.org/abs/2609.01992v1)*
