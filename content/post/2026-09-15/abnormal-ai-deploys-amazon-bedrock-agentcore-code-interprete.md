---
title: "Abnormal AI Deploys Amazon Bedrock AgentCore Code Interpreter for Email Threat Detection"
slug: "abnormal-ai-deploys-amazon-bedrock-agentcore-code-interpreter-for-email-threat-detection"
description: "Abnormal AI, a behavioral security service protecting over 25 percent of the Fortune 500, has deployed Amazon Bedrock AgentCore Code Interpreter to support its real-time email threat detection..."
date: 2026-09-15T22:08:30+05:30
tags: [AIagents, Cybersecurity, AmazonBedrock, MachineLearning]
categories: ["AI", "Artificial Intelligence", "Cybersecurity", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-21301-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Abnormal AI Deploys Amazon Bedrock AgentCore Code Interpreter for Email Threat Detection

Abnormal AI, a behavioral security service protecting over 25 percent of the Fortune 500, has deployed Amazon Bedrock AgentCore Code Interpreter to support its real-time email threat detection systems. The integration provides a dedicated compute scratch pad for agents, allowing them to process billions of messages and execute code at scale to block threats before they reach the inbox.

## 🔍 Overview
Abnormal AI has adopted an AI-native approach for both its production runtime and its internal development processes. Key operational metrics include:
* **Scale:** Production systems handle billions of operations daily.
* **Agent-Driven Development:** 80 percent of the company's code changes are built using an agent.
* **Autonomous Creation:** 40 percent of code changes are built end-to-end by background agents, categorized as fully AI built rather than AI assisted.

## 🧩 How it works
Abnormal AI processes email messages through a three-tiered detection architecture designed for efficiency and depth.

| Tier | Components | Function |
| :--- | :--- | :--- |
| Tier 1 | Small models, heuristic rules, and lightweight classifiers (logistic regressions) | Handles the largest volume of traffic where deep analysis is unnecessary. |
| Tier 2 | Deep learning and machine learning (ML) models | Performs behavioral signal analysis on messages where Tier 1 is unconfident. |
| Tier 3 | Inline agents using Code Interpreter | Evaluates the hardest cases that typically require human analysts by writing and running scripts dynamically. |

## ⚙️ Key details
Amazon Bedrock AgentCore Code Interpreter provides a fully managed, serverless runtime that enhances an agent's capabilities beyond semantic reasoning alone. 
* **Flexible Integration:** The capability is exposed as an API, allowing teams with existing infrastructure to use it as a plug-and-play component without dictating specific workflows.
* **Functionality:** Agents can use the sandbox to run commands, upload files, and retrieve results for data aggregation, analysis, and verification.
* **Session Persistence:** The system supports long-running batch jobs exceeding 30 minutes and day-long operations where the agent re-invokes Code Interpreter intermittently, such as training an external model and then processing the results.

## 💡 Why it matters
By pairing large language models with a code execution environment, agents can perform complex reasoning and verification tasks. At Abnormal AI, these agents analyze threat intelligence data and evaluate how it fits into a behavioral model to make final determinations on high-difficulty cases, while separate monitoring and learning systems verify the live system and handle misclassifications.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-21301-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-21301-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/11/ML-21301-3.png)

#AIagents #Cybersecurity #AmazonBedrock #MachineLearning

---

*Source: [Abnormal AI: Amazon Bedrock AgentCore for agentic email security at scale | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/abnormal-ai-amazon-bedrock-agentcore-for-agentic-email-security-at-scale/)*
