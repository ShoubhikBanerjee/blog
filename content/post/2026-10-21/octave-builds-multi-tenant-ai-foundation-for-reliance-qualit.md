---
title: "Octave Builds Multi-Tenant AI Foundation for Reliance Quality Management System"
slug: "octave-builds-multi-tenant-ai-foundation-for-reliance-quality-management-system"
description: "Octave has developed a three-layer AI foundation using Cohere Embed v4 on Amazon Bedrock to enable secure AI capabilities within its cloud-native quality management system, Reliance. This horizontal..."
date: 2026-10-21T12:01:55+05:30
tags: [Octave, AmazonBedrock, Cohere, MultiTenancy, QualityManagement]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Enterprise Software"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21094-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Octave Builds Multi-Tenant AI Foundation for Reliance Quality Management System

Octave has developed a three-layer AI foundation using Cohere Embed v4 on Amazon Bedrock to enable secure AI capabilities within its cloud-native quality management system, Reliance. This horizontal platform was designed to handle 2 billion documents while maintaining strict tenant isolation for customers in the medical device, pharmaceutical, and food manufacturing sectors.

## 🔍 Overview

Octave operates in 180 countries and serves more than 60% of the Global Fortune 500. Its Reliance platform supports over 650 enterprise customers with 40+ applications, including:
* Complaint management
* CAPA tracking
* Audit management
* Supplier quality

To implement AI, Octave identified four high-impact use cases: complaint summarization and triage, audit readiness monitoring, incident narrative generation, and predictive quality risk scoring. The team first deployed a Complaint Triage Assistant to prove the architecture.

## 🧩 How it works

The foundation consists of three layers designed to ensure that no data crosses tenant boundaries:

| Layer | Function | Technology Used |
| :--- | :--- | :--- |
| Data Preparation | Embeds quality documents and writes them to per-tenant vector stores | Cohere Embed v4 on Amazon Bedrock; Amazon OpenSearch Service |
| Secure Execution | Applies authentication and policy before calling an isolated microVM session | Amazon Bedrock AgentCore (AgentCore Gateway); Anthropic Claude on Amazon Bedrock |
| Content Protection | Applies input and output filtering | Amazon Bedrock Guardrails |

## ⚙️ Key details

Octave addressed several technical and regulatory obstacles to ensure security and performance:

* **Tenant Isolation:** Vector stores, retrieval logic, and generation context are scoped to a single tenant. Permissions for tools, data stores, and model endpoints are scoped to the requesting user rather than a shared service role.
* **Threat Mitigation:** The system is designed to defend against OWASP Top 10 for LLM Applications (2025) threats, including prompt injection (LLM01), sensitive information disclosure (LLM02), improper output handling (LLM05), and excessive agency (LLM06).
* **Scalability:** The pipeline embedded 2 billion documents, including Word files, PDFs, scanned forms, spreadsheets, images, and email. The system is designed to onboard the largest tenants within a single working day.

## 💡 Why it matters

In a platform serving over 14,000 customers, inadvertent disclosure of complaint records, audit findings, or corrective actions would carry regulatory consequences outweighing AI benefits. By building a horizontal platform first, Octave has cut deployment time per use case by 50 percent.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21094-1.png)

#Octave #AmazonBedrock #Cohere #MultiTenancy #QualityManagement

---

*Source: [How Octave built a secure multi-tenant AI foundation on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-octave-built-a-secure-multi-tenant-ai-foundation-on-amazon-bedrock/)*
