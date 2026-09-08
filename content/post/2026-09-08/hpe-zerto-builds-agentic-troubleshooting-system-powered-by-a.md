---
title: "HPE Zerto Builds Agentic Troubleshooting System Powered by Amazon Bedrock"
description: "HPE Zerto, in collaboration with AWS, has developed an agentic troubleshooting system powered by Amazon Bedrock. This system addresses the challenges data protection and disaster recovery teams face..."
date: 2026-09-08T22:06:20+05:30
tags: [AWS, AmazonBedrock, HPEZerto, DisasterRecovery, AIagents]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/01/ML-20849-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# HPE Zerto Builds Agentic Troubleshooting System Powered by Amazon Bedrock

HPE Zerto, in collaboration with AWS, has developed an agentic troubleshooting system powered by Amazon Bedrock. This system addresses the challenges data protection and disaster recovery teams face as their environments grow in scale, complexity, and business criticality.

## 🔍 Overview

Data protection and disaster recovery teams must continuously monitor protection health, validate service level agreement (SLA) compliance, interpret alerts, investigate failures, and prepare for recovery events. This work often spans multiple sites and large numbers of protected workloads. 

Historically, the information needed to answer operational questions has been fragmented across product alerts, events, and documentation. This fragmentation forces teams to manually gather context, losing valuable time moving between dashboards, reports, and knowledge sources to understand what is happening and how to act. These delays become especially significant during outages or cyber events, where the cost of uncertainty is high and teams require clear, trusted guidance quickly.

To address this, HPE Zerto built an agentic troubleshooting system deployed directly in your on-premises environment with controlled and secure access to operational signals, environmental context, and product knowledge.

## 🧩 How it works

The system is deployed as a pod inside the Zerto product within your on-premises environment. This allows you to access its capabilities directly from the same user interface used for day-to-day operations. 

Users can interact with the system using natural language. The assistant is designed to reason, act, and respond with contextual, actionable answers grounded in the live state of your environment, helping you move quickly from questions to actionable insights.

## ⚙️ Key details

Amazon Bedrock was selected to power the system due to its ability to support secure enterprise deployment, model flexibility, and operational control. The architecture incorporates several AWS services and security features:

| Component / Feature | Functionality |
| :--- | :--- |
| **Amazon Bedrock Guardrails** | Enforces content security to ensure prompts and system output align with company policy, compliance, and security requirements. |
| **Server-Sent Events (SSE)** | Delivers real-time streaming to show investigation progress as it happens, improving the user experience. |
| **AWS Identity and Access Management (IAM)** | Manages per-tenant request tagging using the specific IAM role tags each tenant assumes. |
| **Amazon CloudWatch** | Receives telemetry data sent from the system to provide visibility into agent performance, error rates, and usage patterns. |

## 💡 Why it matters

Integrating generative AI directly into disaster recovery environments delivers several operational benefits:

* **Reduced Downtime**: These capabilities help substantially reduce data loss and downtime while supporting rapid recovery from ransomware events, outages, and other disruptions.
* **Operational Guidance**: Less experienced administrators can more easily interpret complex symptoms and determine the safest remediation paths.
* **Fast Risk Summaries**: Managers gain rapid access to clear summaries of risk, SLA exposure, and recovery readiness.
* **Reduced Operational Burden**: Customers can turn complex resilience data into actionable answers without adding additional operational overhead, even when deployed across different environments.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/01/ML-20849-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/01/ML-20849-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/01/ML-20849-3.png)

#AWS #AmazonBedrock #HPEZerto #DisasterRecovery #AIagents

---

*Source: [How HPE Zerto built an agentic troubleshooting system with Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-hpe-zerto-built-an-agentic-troubleshooting-system-with-amazon-bedrock/)*
