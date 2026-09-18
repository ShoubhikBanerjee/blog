---
title: "Amazon Bedrock launches enhanced AgentCore runtime for scalable AI agents"
slug: "amazon-bedrock-launches-enhanced-agentcore-runtime-for-scalable-ai-agents"
description: "Amazon announced an update to its Bedrock AgentCore runtime, adding new speed, flexibility, and cost‑efficiency features for production AI agents."
date: 2026-09-18T22:02:10+05:30
tags: [AmazonBedrock, AgentCore, AIagents]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "AI Agents", "Serverless"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21766-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock launches enhanced AgentCore runtime for scalable AI agents

Amazon announced an update to its Bedrock AgentCore runtime, adding new speed, flexibility, and cost‑efficiency features for production AI agents.

## 🔍 Overview
- Agents are no longer experiments; they process claims, write and review code, coordinate across systems, and run for hours without supervision.
- Amazon Bedrock AgentCore helps developers build, connect, and optimize agents securely at scale.
- The AgentCore runtime provides a fully managed compute layer to deploy and run agents without building or maintaining infrastructure.
- Thousands of teams have used AgentCore runtime to run production agents since its launch.

## 🧩 How it works
- Each agent runs in a hardware‑enforced isolated session.
- A session allocates memory at start and holds it until the session ends; the new runtime reclaims memory immediately when a session releases it.
- When no work is present, the platform scales to zero—nothing runs and nothing is charged.
- When work arrives, the platform provisions the required capacity.
- Cold‑start times are now consistent regardless of container size or concurrency, with sessions starting from a small memory profile and paging in additional memory on demand.

## ⚙️ Key details
- Serverless execution with session isolation.
- Scale‑to‑zero and pay‑only‑for‑use billing.
- Improved memory management: memory is released back instantly at session end and reclaimed when a session goes cold.
- Predictable startup: sessions that land on an already‑initialized environment start in under 100 ms; otherwise, the runtime handles booting, image pulling, and agent initialization.
- The runtime tracks usage so billing reflects the actual work performed.

## 🚀 Availability
- The enhanced AgentCore runtime is announced today as an update to the existing service.
- It builds on the first version’s foundation of serverless, session isolation, and scale‑to‑zero.

## 💡 Why it matters
- Developers can focus on building agents rather than managing scalable infrastructure.
- Faster, predictable startup improves user experience for production agents.
- Lower memory consumption and pay‑as‑you‑go billing reduce operational costs.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21766-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/17/ML-21766-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/06/03/ML-20817-5.png)

#AmazonBedrock #AgentCore #AIagents

---

*Source: [The new AgentCore runtime: Elastic, optimized, and consistently fast starts | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/the-new-agentcore-runtime-elastic-optimized-and-consistently-fast-starts/)*
