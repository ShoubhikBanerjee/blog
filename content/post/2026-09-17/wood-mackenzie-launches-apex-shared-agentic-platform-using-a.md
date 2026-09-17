---
title: "Wood Mackenzie Launches APEX Shared Agentic Platform Using Amazon Bedrock AgentCore"
slug: "wood-mackenzie-launches-apex-shared-agentic-platform-using-amazon-bedrock-agentcore"
description: "Wood Mackenzie has developed APEX (Agentic Platform for Energy eXperience), a shared platform designed to allow teams to ship AI agents without reinventing underlying infrastructure."
date: 2026-09-17T22:02:13+05:30
tags: [AIagents, AmazonBedrock, EnterpriseAI, AgentCore, WoodMackenzie]
categories: ["AI", "AI Agents", "Enterprise Software", "Cloud Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/16/ML-21057-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Wood Mackenzie Launches APEX Shared Agentic Platform Using Amazon Bedrock AgentCore

Wood Mackenzie has developed APEX (Agentic Platform for Energy eXperience), a shared platform designed to allow teams to ship AI agents without reinventing underlying infrastructure.

## 💡 Why it matters
There is a wide gap between AI experimentation and production. Industry surveys through early 2026 indicate enterprise AI experimentation is near universal, yet only about a quarter of organizations have scaled agents into production in even one function. Internally at Wood Mackenzie, 88 percent of AI proofs-of-concept never reach widescale deployment.

Failures are largely attributed to architectural issues rather than model-related ones:
* **Evaluation and Observability:** This is the most-named blocker; teams cannot reliably predict when non-deterministic agents will be wrong, and standard regression tests often fail to catch it.
* **Governance and Identity:** Many executives report an inability to immediately shut down misbehaving agents.
* **Infrastructure Duplication:** Teams frequently rebuild authentication, guardrails, memory, and tracing from scratch, often hardcoding models which makes swapping providers require code rewrites.
* **System Behavior:** Forrester attributes failures to ambiguity, miscoordination, and unpredictable system behavior.

## 🧩 How it works
APEX is built on Amazon Bedrock AgentCore, a managed platform used to build, connect, and optimize agents at scale. By using a shared runtime for orchestration, safety, observability, identity, and connectivity, teams can focus on business logic rather than "backend plumbing."

Before APEX, three applications—Woody, Lens AI, and the ST Trading App—were each building their own agent stacks. A shared platform prevents the "infrastructure tax" of duplicating runtimes and ensures these stacks can share tools, memory, and evaluation.

## ⚙️ Key details
Wood Mackenzie selected AgentCore over self-hosted solutions based on requirements for hosting models, cost models, scalability, governance, enterprise support, and whether the system is model agnostic.

**Platform Capabilities:**
* **Model and Framework Agnostic:** Works with any model (regardless of whether it runs on Amazon Bedrock) and any open source framework, including:
    * Strands Agents
    * LangGraph
    * LangChain
    * LlamaIndex
    * CrewAI
    * Google ADK
    * OpenAI Agents SDK
* **Protocol Support:** Supports both the Model Context Protocol (MCP) and the Agent-to-Agent (A2A) protocol.
* **Managed Infrastructure:** AWS handles patching, availability, and scaling, removing the need to operate a cluster.
* **Control Plane:** APEX Studio provides a single control plane for operations.
* **Deployment:** Serves both internal users (Woody) and external consumers (Lens) under identity-aware entitlements.

#AIagents #AmazonBedrock #EnterpriseAI #AgentCore #WoodMackenzie

---

*Source: [A shared agentic platform for Wood Mackenzie, on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/a-shared-agentic-platform-for-wood-mackenzie-on-amazon-bedrock-agentcore/)*
