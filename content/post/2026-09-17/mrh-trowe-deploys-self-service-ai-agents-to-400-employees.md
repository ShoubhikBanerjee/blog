---
title: "MRH Trowe Deploys Self-Service AI Agents to 400 Employees"
slug: "mrh-trowe-deploys-self-service-ai-agents-to-400-employees"
description: "MRH Trowe, a commercial and industrial insurance broker operating in Germany, Switzerland, and Austria, has provided approximately 400 employees with secure access to self-service AI agents. The..."
date: 2026-09-17T22:02:13+05:30
tags: [AWS, AIagents, InsuranceTech, LibreChat, AmazonBedrock]
categories: ["AI", "AI Agents", "Cloud Computing", "Enterprise Software"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/15/ML-21177-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# MRH Trowe Deploys Self-Service AI Agents to 400 Employees

MRH Trowe, a commercial and industrial insurance broker operating in Germany, Switzerland, and Austria, has provided approximately 400 employees with secure access to self-service AI agents. The rollout reached this scale within the first month of production as part of a strategic corporate goal to enhance efficiency and streamline internal processes.

## 🧩 How it works

MRH Trowe utilizes a framework combining three primary components to manage its AI agents:

| Component | Role |
| :--- | :--- |
| Strands Agents | An open source SDK used to create agents in a few lines of code, handling orchestration and reasoning patterns. |
| Amazon Bedrock AgentCore | A platform used to build, connect, and optimize agents at scale. It isolates each agent session at the compute and filesystem level. |
| LibreChat | An open source AI chat interface that provides the user-facing environment. |

## ⚙️ Key details

The implementation includes several specific controls and features:

* **Security and Compliance**: The solution uses Microsoft Entra ID for authentication, passing user identity server-side to ensure agents only access that specific employee's data. To meet German financial sector requirements, all agents, models, and data run in the AWS Europe (Frankfurt) Region.
* **LibreChat Capabilities**: The interface includes a branded customizable UI, conversation management, multi-model support to avoid vendor lock-in, and a token budget system to prevent unexpected costs.
* **Cost Management**: Initial production costs were approximately $14 per seat in the first month. MRH Trowe identifies a path to reduce infrastructure costs by about 40 percent via scheduled scaling and right-sizing.

## 💡 Why it matters

MRH Trowe aims for a vision where repetitive processes are automated by those who previously performed them, and AI provides the first answer to every question before human intervention. 

As a first production example, the company deployed an agent that converts Microsoft Teams meetings into meeting minutes. When an employee asks in German for a recent meeting with a specific participant, the agent retrieves the transcript from the employee's calendar and drafts a structured summary including the date, participants, agenda, topics, and action items.

#AWS #AIagents #InsuranceTech #LibreChat #AmazonBedrock

---

*Source: [How MRH Trowe enabled secure self-service AI agents in financial services | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-mrh-trowe-enabled-secure-self-service-ai-agents-in-financial-services/)*
