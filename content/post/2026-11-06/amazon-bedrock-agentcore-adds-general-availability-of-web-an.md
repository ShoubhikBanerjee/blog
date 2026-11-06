---
title: "Amazon Bedrock AgentCore adds General Availability of Web Answer tool"
slug: "amazon-bedrock-agentcore-adds-general-availability-of-web-answer-tool"
description: "Today Amazon announced the general availability of Web Answer on Amazon Bedrock AgentCore."
date: 2026-11-06T06:03:11+05:30
tags: [AmazonBedrock, WebAnswer, AIAgents]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22248-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore adds General Availability of Web Answer tool

Today Amazon announced the general availability of Web Answer on Amazon Bedrock AgentCore.

## 🔍 Overview
- Web Answer returns a synthesized, source‑cited answer to a natural‑language question with a single tool call.
- It collapses the traditional search, retrieve, synthesize, and citation pipeline into one request.
- Agents receive a cited answer in seconds.

## 🧩 How it works
1. Your agent sends a question to the **AgentCore Gateway**.
2. The Gateway authenticates the call with **AWS IAM** or a **JSON Web Token (JWT)**.
3. The Gateway invokes **Web Answer**, a managed connector owned by AWS, using its service role.
4. Web Answer **plans searches**, runs several in parallel, and reads key pages to verify facts.
5. If evidence is insufficient, Web Answer searches again.
6. It writes an answer that ties each claim to its source URL.
7. The Gateway returns the answer and its citations to the agent as a **Model Context Protocol (MCP) tool result**.

## ⚙️ Comparison with Web Search
| Feature | Web Search | Web Answer |
|---------|------------|------------|
| Output | Returns ranked URLs, titles, snippets, and metadata. | Returns a synthesized answer with citations.
| Control | Gives full control over how results are processed. | Handles retrieval, synthesis, and attribution automatically.
| Use case | When you want full control over result handling. | When the question is a sub‑task inside a larger agent and you do not want to own a retrieval pipeline.

## 🚀 Availability
- Web Answer is **generally available** on Amazon Bedrock AgentCore.
- A Gateway administrator can add Web Answer as a target on an existing AgentCore Gateway; the tool then appears to any attached agent via `tools/list` and `tools/call`.
- The example deployment uses an **AgentCore Gateway in us-east-1** with **IAM (AWS_IAM) inbound authentication**.
- Both the Gateway and Web Answer invocations are **billable**.
- The Gateway checks permission on each request against the ARN `arn:aws:bedrock-agentcore:us-east-1:aws:tool/web-answer.v1`.
- Adding Web Answer as a connector target and getting started takes **minutes**.

## 💡 Why it matters
- Developers no longer need to build and maintain a separate search‑retrieve‑synthesize‑citation pipeline.
- Each query triggers fresh web searches, and the model receives today’s date, ensuring answers are based on up‑to‑date information.
- Providing a fully managed, source‑cited answer simplifies the construction of complex agents that need reliable, real‑time knowledge.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22248-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22248-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22248-3.jpg)

#AmazonBedrock #WebAnswer #AIAgents

---

*Source: [Getting started with Web Answer on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/getting-started-with-web-answer-on-amazon-bedrock-agentcore/)*
