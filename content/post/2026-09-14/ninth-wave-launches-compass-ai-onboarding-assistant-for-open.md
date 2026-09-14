---
title: "Ninth Wave Launches Compass AI Onboarding Assistant for Open Finance"
slug: "ninth-wave-launches-compass-ai-onboarding-assistant-for-open-finance"
description: "Ninth Wave has introduced Compass, an AI-enabled onboarding assistant designed to streamline the integration of financial institutions into the open finance network. By utilizing Amazon Bedrock..."
date: 2026-09-14T22:04:39+05:30
tags: [OpenFinance, AIAgents, AWS, Fintech, AmazonBedrock]
categories: ["AI", "Artificial Intelligence", "Financial Technology", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/13/ML-21160-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Ninth Wave Launches Compass AI Onboarding Assistant for Open Finance

Ninth Wave has introduced Compass, an AI-enabled onboarding assistant designed to streamline the integration of financial institutions into the open finance network. By utilizing Amazon Bedrock AgentCore, Compass assists bank engineers and integration teams in validating APIs, mapping fields, and scoring production readiness.

## 💡 Why it matters
Financial institutions often face persistent integration challenges when exposing APIs, as each bank uses unique field names and formatting conventions. Traditionally, this process has required weeks of manual effort across email threads and spreadsheets. Compass automates these tasks to improve efficiency and maintain consistent information across teams.

## 🧩 How it works
Compass utilizes a multi-agent architecture to manage complex onboarding tasks. This approach allows specific agents to focus on individual responsibilities, such as mapping, analysis, and interactive Q&A, without competing for prompt space. 

*   **Intent-based routing:** The orchestrator classifies user intent and routes tasks to the appropriate specialist agent.
*   **Per-task model selection:** Lightweight models handle high-volume tasks, while higher-reasoning models are reserved for complex analysis and mapping.
*   **Tenant-scoped grounding:** Before an agent is invoked, the application assembles context specific to the individual bank, ensuring that one bank's data remains isolated from another.

## ⚙️ Key details
Ninth Wave maintains strict security and compliance standards within the Compass environment, including:

*   **Data Isolation:** Multi-tenant data isolation and content-safety controls.
*   **Compliance:** Alignment with SOC 2 and PCI DSS requirements, utilizing encryption at rest and in transit.
*   **Infrastructure Security:** Use of AWS WAF, AWS Identity and Access Management (IAM), and AWS Secrets Manager for credential management.
*   **Auditability:** Comprehensive audit logging for all supported AWS API activity via AWS CloudTrail.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21160-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-21160-2.png)

#OpenFinance #AIAgents #AWS #Fintech #AmazonBedrock

---

*Source: [How Ninth Wave built AI-powered open finance onboarding on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-ninth-wave-built-ai-powered-open-finance-onboarding-on-amazon-bedrock/)*
