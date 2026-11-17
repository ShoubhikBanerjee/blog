---
title: "Amazon Bedrock Managed Knowledge Base and AgentCore Memory Integration"
slug: "amazon-bedrock-managed-knowledge-base-and-agentcore-memory-integration"
description: "Amazon Bedrock Managed Knowledge Base and Amazon Bedrock AgentCore memory have been updated to include integrated conversation storage, fact extraction, and intelligent retrieval. This capability..."
date: 2026-11-17T12:12:52+05:30
tags: [AmazonBedrock, GenerativeAI, AIAgents, CloudComputing]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Services"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-21969-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Managed Knowledge Base and AgentCore Memory Integration

Amazon Bedrock Managed Knowledge Base and Amazon Bedrock AgentCore memory have been updated to include integrated conversation storage, fact extraction, and intelligent retrieval. This capability allows developers to streamline the process of maintaining context across sessions by automating fact-based retrieval and knowledge base interactions.

## 🧩 How it works

By adding a `memoryConfiguration` to the `AgenticRetrieveStream` request, AgentCore memory functions as a retrieval source alongside a knowledge base. The integration follows these operational steps:

* **Conversation Management:** The service stores each conversation and extracts facts from it.
* **Planning:** The planner autonomously decides when a stored fact about the user is relevant.
* **Query Composition:** Retrieved facts are used to compose sub-queries sent to the knowledge base.
* **Persistence:** After an answer is generated, the service saves the turn back to memory.

## ⚙️ Key details

The integration enables robust access control and user-specific memory, as illustrated by the following table of operational roles:

| Component | Role |
| :--- | :--- |
| Amazon Cognito | Authenticates employees and provides sub and email claims |
| AgentCore Memory | Stores facts, conversation history, and user context |
| Managed Knowledge Base | Performs ACL-enabled retrieval based on user context |
| Planner | Determines when to use long-term memory to aid sub-queries |

## 💡 Implementation Requirements

* **Opt-in Compatibility:** The feature is opt-in and backward compatible.
* **Security:** The application remains responsible for authenticating the user and passing identity information. The `userContext` ensures the knowledge base returns only documents permitted by the user's access control lists (ACLs).
* **IAM Roles:** The handler assumes the application’s IAM role using the user ID as a session tag.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-21969-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-21969-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-21969-3.png)

#AmazonBedrock #GenerativeAI #AIAgents #CloudComputing

---

*Source: [Build memory-aware AI agents with Agentic Retrieve on Amazon Bedrock Managed Knowledge Base | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-memory-aware-ai-agents-with-agentic-retrieve-on-amazon-bedrock-managed-knowledge-base/)*
