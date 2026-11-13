---
title: "Natera Improves Lab Operations with Agentic AI System SWARM"
slug: "natera-improves-lab-operations-with-agentic-ai-system-swarm"
description: "Natera has deployed SWARM (Systematic Workflow Analytics and Resolutions Manager), an agentic AI system built with Amazon Bedrock AgentCore, to optimize lab instrument maintenance and reduce..."
date: 2026-11-13T22:02:12+05:30
tags: [AWS, AmazonBedrock, AgenticAI, Natera, LabOps]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21653-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Natera Improves Lab Operations with Agentic AI System SWARM

Natera has deployed SWARM (Systematic Workflow Analytics and Resolutions Manager), an agentic AI system built with Amazon Bedrock AgentCore, to optimize lab instrument maintenance and reduce downtime. By digitizing institutional knowledge, the system assists service engineers in diagnosing equipment issues more efficiently.

## 🔍 Overview
Natera’s lab operations previously faced challenges with instrument downtime, leading to delays in sample processing and patient reporting. With an average first response time of 17.4 hours and over 65 tickets daily, the team sought a solution to leverage deep institutional knowledge rather than relying on fragmented, individual expertise.

## 🧩 How it works
SWARM utilizes a two-runtime architecture that shares a single library of skills to address maintenance tickets:

| Component | Function |
| :--- | :--- |
| swarm-agent | Autonomously generates structured diagnostic reports before an engineer opens a ticket |
| swarm-hive | Allows engineers to interact in real time, upload images, and explore troubleshooting paths |

The system operates across four primary layers:
* **Event layer**: Routes Jira tickets using Amazon EventBridge and Amazon SQS.
* **Agent layer**: Hosts the swarm-agent, swarm-hive, and the skill library.
* **Context layer**: Accesses vendor manuals, historical tickets, and operational data.
* **Observability and delivery layer**: Captures logs, traces, and metrics.

## ⚙️ Key details
Natera opted for Amazon Bedrock AgentCore to handle infrastructure orchestration, security, and scaling. Key security measures include:
* **Keyless deployment**: Uses OIDC and AWS STS to generate short-lived, scoped credentials rather than long-lived keys.
* **Least privilege**: AWS IAM enforces access control at the component level.
* **Network isolation**: Amazon VPC with private subnets and endpoints restricts traffic.
* **Credential management**: AWS Secrets Manager automatically rotates existing credentials every 30 days.

## 💡 Why it matters
Since implementing the system, Natera reports a 130x faster first response time and 96.2 percent automated coverage across support tickets. Ariel Jirau, who led the lab engineering team, noted, “The system does not replace engineers—it gives them access to the full depth of institutional knowledge the moment a ticket arrives.”

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21653-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21653-2-1.jpg)

#AWS #AmazonBedrock #AgenticAI #Natera #LabOps

---

*Source: [How Natera designed an agentic AI system for lab ops with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-natera-designed-an-agentic-ai-system-for-lab-ops-with-amazon-bedrock-agentcore/)*
