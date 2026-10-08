---
title: "Amazon Quick adds real‑time ACL checks to Bedrock Knowledge Bases for secure RAG"
slug: "amazon-quick-adds-realtime-acl-checks-to-bedrock-knowledge-bases-for-secure-rag"
description: "Enterprise organizations are adopting Retrieval Augmented Generation (RAG) to unlock insights from company knowledge sources like Microsoft SharePoint, Google Drive, and Atlassian Confluence. Because..."
date: 2026-10-08T12:07:03+05:30
tags: [RAG, AmazonBedrock, AIsecurity, EnterpriseAI]
categories: ["AI", "Artificial Intelligence", "Enterprise Computing", "Cloud Services"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-22080-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Quick adds real‑time ACL checks to Bedrock Knowledge Bases for secure RAG

Enterprise organizations are adopting Retrieval Augmented Generation (RAG) to unlock insights from company knowledge sources like Microsoft SharePoint, Google Drive, and Atlassian Confluence. Because those sources contain sensitive information governed by complex permission structures, making sure AI‑generated answers respect those permissions is one of the hardest challenges in enterprise AI.

## 🔍 Overview
- RAG solutions must enforce access controls that match the source systems.
- A single unauthorized document in an AI response could expose confidential strategy, unreleased financial data, or sensitive HR information.
- Organizations want to democratize AI‑powered insights **without** compromising their existing security posture.

## ⚠️ Weaknesses of snapshot‑based ACLs
- Data source connectors (e.g., SharePoint connector) pull ACLs during periodic sync jobs.
- ACLs are stored as attributes in an index and used for pre‑retrieval filtering.
- This model places sole enforcement responsibility on the AI system, which is not the authoritative source of permissions.
- Pull‑based syncs create a snapshot; the ACLs reflect the state **at the last sync**.
- Sources like Confluence do not emit events when group membership changes, so revoked access may still be honored until the next sync.
- New permission features or changes to sharing models can create gaps in the ACL mapping logic.

## ✅ Real‑time ACL enforcement in Amazon Quick & Bedrock Knowledge Bases
When a user queries an Amazon Quick agent backed by a Google Drive knowledge base, the system enforces access controls in two stages:

1. **Pre‑retrieval filtering** – Amazon Quick performs a semantic search against the vector index, then applies the stored ACL attributes. This reduces the number of documents that need real‑time checks.
2. **Real‑time verification** – For the candidate documents, Amazon Quick calls the Google Drive APIs using a service‑account credential supplied by the administrator. It generates user‑specific access tokens through impersonation, and Google Drive, the source of truth for ACLs, confirms whether the user can view each document. Unauthorized documents are excluded before the passages are passed to the large language model (LLM).

| Stage               | Action                                                                                     |
|---------------------|--------------------------------------------------------------------------------------------|
| Pre‑retrieval       | Semantic search + apply stored ACL attributes (index‑based filter)                         |
| Real‑time verification | Call source API (Google Drive) with impersonated token; exclude documents without access |

Additional safeguards such as Amazon Bedrock Guardrails, grounding checks, and configurable safety policies are applied to the LLM context.

## 💡 Why it matters
- **Always‑current permissions** – No security gaps between sync cycles; revoking a user’s access is reflected in AI responses within moments, not hours or days.
- **Compliance assurance** – The authoritative source (Google Drive, SharePoint, etc.) validates every document at query time.
- **Scalable cost** – The two‑stage approach avoids costly real‑time API calls for every indexed passage while still guaranteeing up‑to‑date enforcement.

The combined solution lets enterprises democratize AI insights while maintaining strict security and compliance controls.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-22080-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-22080-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/07/ML-22080-3.jpg)

#RAG #AmazonBedrock #AIsecurity #EnterpriseAI

---

*Source: [Rethinking access control for RAG with Amazon Quick and Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/rethinking-access-control-for-rag-with-amazon-quick-and-amazon-bedrock/)*
