---
title: "ProvenanceGuard Introduces Post-Generation Verification for MCP Agents"
slug: "provenanceguard-introduces-post-generation-verification-for-mcp-agents"
description: "ProvenanceGuard has been developed as a post-generation verification layer that operates on top of black-box MCP agents to verify the accuracy of agent-produced answers."
date: 2026-09-29T22:02:51+05:30
tags: [MCP, AIagents, Verification, NLI, ProvenanceGuard]
categories: ["AI", "Machine Learning", "AI Agents", "Natural Language Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/668e37fd9c9aa124a3c867e8/phhhj_BLOJbvnTFhVaZ5y.png"
author: "Shoubhik Banerjee"
draft: false
---

# ProvenanceGuard Introduces Post-Generation Verification for MCP Agents

ProvenanceGuard has been developed as a post-generation verification layer that operates on top of black-box MCP agents to verify the accuracy of agent-produced answers.

## 🧩 How it works

The system runs after an agent produces an answer and reads the captured MCP trace, including tool outputs and source IDs, without requiring the agent to be retrained. The verification process follows these steps:

* **Claim Decomposition**: A local language model breaks the answer into specific claims.
* **Source Identification**: MiniLM is used to find the source most relevant to each claim.
* **Support Verification**: A DeBERTa NLI verifier model checks if the source actually supports the claim.
* **Comparison**: The system compares the identified source with the one the answer names or implies.
* **Verdict**: It emits a per-claim source verdict and a global answer-level allow or block decision.

## ⚙️ Key details

* **Literal Value Checking**: The verifier closely checks numbers, dates, or identifiers; if they are absent from the source, they cannot pass based on plausibility alone.
* **Repair Mechanism**: Blocked answers can undergo a RARR-style repair step for a source-grounded revision or safe fallback, which is then re-verified.
* **Transparency**: Unlike other checkers, ProvenanceGuard records the connection between each claim and its supporting tool output for reviewer oversight.

## 📊 Performance and Testing

ProvenanceGuard was tested using 281 real traces from a medical agent utilizing research articles and patient records. In a main test where human experts checked 361 claims from 40 answers:

* It caught 138 of 139 claims that experts said should not pass.
* It let one claim through.
* It flagged 67 claims for review or repair that experts considered supported.
* It identified the correct source for claims with an identifiable source approximately 86% of the time.

When compared to other support checkers, ProvenanceGuard scored highest on the measure of catching claims that should be blocked while avoiding unnecessary blocks:

| System | Score | Provides Tool Output Connection |
| :--- | :--- | :--- |
| ProvenanceGuard | 0.802 | Yes |
| MiniCheck | 0.783 | No |
| RAGAS Faithfulness | 0.758 | No |
| AlignScore | 0.662 | No |
| SummaC-ZS | 0.436 | No |

#MCP #AIagents #Verification #NLI #ProvenanceGuard

---

*Source: [Getting the Source Right, Not Just the Fact: Source-Aware Verification for MCP Agents](https://huggingface.co/blog/MultiverseComputingCAI/getting-the-source-right-not-just-the-fact-source)*
