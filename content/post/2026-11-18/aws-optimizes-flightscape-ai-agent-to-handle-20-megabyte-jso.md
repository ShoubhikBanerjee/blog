---
title: "AWS Optimizes Flightscape AI Agent to Handle 20 Megabyte JSON Payloads"
slug: "aws-optimizes-flightscape-ai-agent-to-handle-20-megabyte-json-payloads"
description: "We have updated the design of Flightscape's Training Schedule Optimization agent using three composable strategies to handle production payloads of over 20 MB of JSON. Flightscape is an airline..."
date: 2026-11-18T06:16:59+05:30
tags: [AmazonBedrock, LangGraph, AIagents, AWS]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/13/ML-21786-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Optimizes Flightscape AI Agent to Handle 20 Megabyte JSON Payloads

We have updated the design of Flightscape's Training Schedule Optimization agent using three composable strategies to handle production payloads of over 20 MB of JSON. Flightscape is an airline operations platform that helps airlines plan and manage their crews, flights, and operations. Built with LangGraph and running on Amazon Bedrock AgentCore, the agent uses an Amazon Bedrock model for reasoning and AgentCore memory to persist chat interactions. By implementing these new strategies, we reduced token consumption by up to 71% and cut average latency by up to 80% across benchmark runs on a representative 23 MB payload.

## 🔍 Overview

As part of Flightscape's crew management capabilities, the Training Schedule Optimization agent verifies crew training schedule assignments against business rules. Equipped with over 40 tools and processing inputs in megabytes, this agent answers complex queries across crew assignments, scheduling, and resource allocation.

Previously, this agent encountered several performance bottlenecks:
* Average request latencies exceeded 15 seconds across most calls.
* Every tool call injected its full payload into the model context, inflating token counts and costs.
* On larger datasets, the context window filled up before the agent could finish reasoning.

## 🧩 How It Works

The optimization workflow relies on a multi-stage data process. The Optimizer receives a Request JSON and produces a Response JSON, which is then validated by a Business Rules Validator to generate a Validation Report JSON. All three JSON documents are ingested by an AI Agent that provides a conversational interface for users to query optimization results, understand validation errors, and explore scheduling assignments.

We defined a custom agent state that holds the data needed by our tools: the optimization request JSON, the optimization response JSON, and the validation report JSON, along with basic statistics and cache data for rich queries. To mitigate token costs, latency, and memory overhead, the agent utilizes three strategies:

* **Strategy 1 (Turn Start & End):** At the start of a turn, the `hydrate_state()` function restores lightweight session state from AgentCore memory. At the end of the turn, the `dehydrate_state()` function writes heavy payloads to the S3ArtifactStore and saves only references to AgentCore memory.
* **Strategies 2 & 3 (Tool Output Handling):** Each time a tool returns a result, if it is an oversized list or dictionary, the agent stores the full result in Amazon Simple Storage Service (Amazon S3) and passes the model a compact summary with a handle. The model can then retrieve more detail as needed with the `get_result_page_tool()`.

## ⚙️ Key Details

Deploying this agent in production requires the following components:
* An AWS account with access to Amazon Bedrock and a supported model.
* An Amazon S3 bucket for artifact storage.
* Amazon Bedrock AgentCore with Amazon Bedrock AgentCore memory enabled for session-state persistence.
* A LangGraph-based agent (or equivalent graph-orchestration framework) with tool-calling support.
* A Python 3.12+ environment with boto3, langchain-core, and langgraph.

The companion code is available in the project's GitHub repository. Additionally, Amazon Bedrock Guardrails can be applied to validate and filter the agent's conversational responses to help facilitate responsible AI practices.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ml-21786-Figure-1.png)

#AmazonBedrock #LangGraph #AIagents #AWS

---

*Source: [Reducing token costs and latency in Amazon Bedrock AgentCore JSON workloads | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/reducing-token-costs-and-latency-in-amazon-bedrock-agentcore-json-workloads/)*
