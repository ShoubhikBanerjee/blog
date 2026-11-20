---
title: "Amazon Upgrades Bedrock AgentCore with Strands Harness and Gateway Interceptors"
slug: "amazon-upgrades-bedrock-agentcore-with-strands-harness-and-gateway-interceptors"
description: "Amazon is upgrading the Amazon Bedrock AgentCore harness to use Strands harness, an open-source agent harness released under an Apache 2.0 license. This update introduces lifecycle hooks, automatic..."
date: 2026-11-20T14:26:01+05:30
tags: [AmazonBedrock, AIagents, AWS, OpenSource, DataSecurity]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing", "Cybersecurity"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22098-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Upgrades Bedrock AgentCore with Strands Harness and Gateway Interceptors

Amazon is upgrading the Amazon Bedrock AgentCore harness to use Strands harness, an open-source agent harness released under an Apache 2.0 license. This update introduces lifecycle hooks, automatic prompt caching, and proactive context management alongside new security features for enterprise-grade tool execution and data protection.

## 🔍 Overview
With this upgrade, the Amazon Bedrock AgentCore harness operates on top of Strands harness, which acts as an assembled agent foundation with recommended instructions, tools, and context management. Amazon Bedrock AgentCore runs this foundation as a managed AWS service, eliminating the need to provision compute, bundle and host the agent loop, manage session scaling, or operate tool-execution infrastructure.

## 🧩 How it works
Each agent session runs in a secure, kernel-isolated microVM in the AgentCore runtime, which connects the harness to the production services required by enterprise agents:
* **Session Execution**: Handled automatically with managed compute, scaling, and high availability.
* **Integration Services**: Connects directly to session persistence, streaming responses, usage metadata, observability, AgentCore memory, Identity, and Gateway.
* **Control Balance**: Developers retain control over instructions, tools, models, permissions, and lifecycle policies while AgentCore manages the underlying execution environment.

## ⚙️ Key details
The upgrade introduces a suite of native features designed to reduce latency, cost, and complexity:
* **Lifecycle Hooks**: Allows developers to apply custom deterministic checks and notifications at defined points in the agent loop.
* **Prompt Caching**: For supported Converse models, the harness caches system prompts, tool definitions, and conversation history to reduce latency and input token costs.
* **Context Optimization**: Summarizes older conversation turns once the context window reaches a configurable threshold, running at about 34% lower token cost than other leading harnesses.

### Built-In Tools
The upgrade brings several new built-in capabilities for managing agent workflows:

| Tool Name | Functionality |
| --- | --- |
| `todo_write` | Maintains a structured task plan that can be restored in later sessions, even after context summarization. |
| `subagent` | Delegates self-contained tasks to fresh worker agents and returns results to the parent. |
| `web_fetch` | Retrieves content from specified webpages to provide up-to-date external context. |
| Filesystem Access | Granular read, write, and edit tools to control the filesystem capabilities granted to agents. |

## 💡 Why it matters
As agents interact with third-party tools, SaaS APIs, and web search engines, sensitive data (such as names, account numbers, or card details) can leave the AWS account and compliance scope through tool arguments. To address this, AgentCore Gateway fronts every tool an agent uses and supports request and response interceptors via AWS Lambda.

By adding Skyflow Detect to AgentCore Gateway as an interceptor, sensitive entities are detected and replaced with reversible vault tokens before data reaches tools, and restored before the agent reads the tool's results. 

This configuration enables three protection modes:
* **Shield the tool**: Strips sensitive values from arguments on the way out and restores them in results on the way back, protecting third-party APIs from receiving customer identities.
* **Shield the model**: De-identifies prompts, history, files, and tool results before the model reads them.
* **Shield the document**: Replaces original document links from tools with clean copies before the agent opens them.

For example, a large European bank uses these tools to investigate card disputes. When an agent searches the web for a merchant, the Skyflow interceptor replaces the customer's name with a reversible token (e.g. `[NAME_AJbrIud]`). The search provider receives a safe query, while the authorized analyst still sees the correct customer details in the agent's final response.

## 🚀 Availability
* **Strands Harness**: Open-source under the Apache 2.0 license.
* **Skyflow Detect Interceptor**: Open source on GitHub.
* **Skyflow Vault**: Available on the AWS Marketplace.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/19/ML-22098-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/18/ML-22128-1.png)

#AmazonBedrock #AIagents #AWS #OpenSource #DataSecurity

---

*Source: [Amazon Bedrock AgentCore harness adds Strands harness defaults, built-in tools, and lifecycle hooks | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-agentcore-harness-adds-strands-harness-defaults-built-in-tools-and-lifecycle-hooks/)*
*Source: [Protect agent tool calls with Skyflow and Amazon Bedrock AgentCore Gateway | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/protect-agent-tool-calls-with-skyflow-and-amazon-bedrock-agentcore-gateway/)*
