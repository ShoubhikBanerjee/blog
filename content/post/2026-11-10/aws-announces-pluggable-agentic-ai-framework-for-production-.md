---
title: "AWS Announces Pluggable Agentic AI Framework for Production‑Scale Multi‑Agent Applications"
slug: "aws-announces-pluggable-agentic-ai-framework-for-productionscale-multiagent-applications"
description: "The Pluggable Agentic AI Framework is a new reference architecture that guides organizations in moving multi‑agent AI applications from prototype to production scale."
date: 2026-11-10T22:09:41+05:30
tags: [AWS, AgenticAI, MultiAgent, Architecture]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Cloud Computing", "Software Architecture"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22256-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Announces Pluggable Agentic AI Framework for Production‑Scale Multi‑Agent Applications

The Pluggable Agentic AI Framework is a new reference architecture that guides organizations in moving multi‑agent AI applications from prototype to production scale.

## 🧩 Overview
- A seven‑layer composable reference architecture for multi‑agent AI.
- Each layer has a distinct responsibility and a stable contract.
- The services shown are examples; alternatives can be substituted to match existing infrastructure.
- The architecture provides a blueprint for building, securing, and operating agentic AI at production scale.

## 📚 Data & Knowledge Layer
- Foundation of Agentic AI; an agent is only as good as the data it can access.
- Owns retrieval, embeddings, and access to structured and unstructured data through a clear contract: *accept a query and return the most relevant information* for context.
- Example building blocks (reference implementation):

| Component | Role |
|---|---|
| Amazon Bedrock Knowledge Base | Stores and serves knowledge for agents |
| Vector Engine for Amazon OpenSearch Serverless | Provides vector search capabilities |
| Amazon S3 Vectors | Persists vector representations |
| Amazon DynamoDB | Offers fast key‑value access |

## ⚙️ Model & Inference Routing Layer
- Model choices are driven by configuration, not hard‑wired logic.
- Use smaller, faster models for simple tasks; larger models for nuanced reasoning.
- A model routing layer keeps agents decoupled from hosting environments and provider‑specific APIs via a consistent request‑and‑response contract.
- A proxy such as **LiteLLM** offers a common interface across providers, enabling model swaps without rewriting application code.

## 🎯 Orchestration Layer
- Determines how work is distributed.
- Simple tasks: a single agent handles end‑to‑end work.
- Complex, cross‑domain workflows: a supervisor delegates to specialist agents, each scoped to a specific capability and toolset.
- Benefits of splitting responsibilities:
  - Keeps each agent’s context focused.
  - Makes latency more predictable.
  - Allows independent testing, scaling, and security modeling.
- Enforce bounded autonomy: specialists execute only within granted tools.
- Supervisor discovers specialists via a **centralized agent registry** and invokes them through standard protocols like **MCP (Model Context Protocol)** and **A2A (Agent to Agent)**.
- Example components: **Strands Agents** for specialists, **Amazon Bedrock AgentCore harness** for orchestrator, **AWS Agent Registry** and **Amazon Bedrock AgentCore Gateway** for discovery and routing.

## 🔐 Security & Guardrails Layer
- Treated as a primary concern from day one.
- All external content is considered untrusted by default.
- Every request—whether from a user, another agent, or an automated workflow—is authenticated, e.g., via **Amazon Bedrock AgentCore Identity**.
- Fine‑grained access control determines whether a tool call is permitted before execution.
- Agents receive temporary, scoped credentials rather than persistent secrets.

## 🔄 Flexibility & Substitution
- While the reference implementation uses specific AWS services, organizations may replace any layer with alternatives that align with their existing infrastructure and requirements.
- The stable contracts between layers ensure that substitutions do not break the overall system.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22256-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22256-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-22256-3.jpg)

#AWS #AgenticAI #MultiAgent #Architecture

---

*Source: [Pluggable Agentic AI Framework: A seven-layer composable enterprise agentic AI reference architecture on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/pluggable-agentic-ai-framework-a-seven-layer-composable-enterprise-agentic-ai-reference-architecture-on-amazon-bedrock-agentcore/)*
