---
title: "Integrating Model Context Protocol Servers with Amazon Quick"
description: "Amazon Quick now supports Model Context Protocol (MCP) integrations, enabling autonomous execution, real-time data access, and specialized AI sub-agent integrations. This integration allows AI agents..."
date: 2026-09-01T06:02:48+05:30
tags: [AWS, AmazonBedrock, MCP, AIAgents, CloudComputing]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/07/08/20742.png"
author: "Shoubhik Banerjee"
draft: false
---

# Integrating Model Context Protocol Servers with Amazon Quick

Amazon Quick now supports Model Context Protocol (MCP) integrations, enabling autonomous execution, real-time data access, and specialized AI sub-agent integrations. This integration allows AI agents to interact with real-world applications, reducing hallucinations while providing stateful, multi-turn capabilities.

## 🧩 How it works

The integration relies on specific components within Amazon Bedrock AgentCore to bridge the gap between user-facing interfaces and backend tools:

| Component | Function |
| :--- | :--- |
| Amazon Quick | Provides chat agents and workflow capabilities in web or desktop apps. |
| AgentCore Gateway | Manages connections and handles the flow between clients and servers. |
| AgentCore Runtime | Hosts MCP server containers with support for session isolation and persistent file systems. |

## ⚙️ Key details

The authorization framework for these integrations is split into two flows:
* **Inbound Auth**: Handles user authentication for access to the MCP server, typically using Amazon Cognito.
* **Outbound Auth**: Uses OAuth 2.0 for machine-to-machine authentication between the Gateway and the Runtime, leveraging AgentCore Identity.

To implement this, you must satisfy several prerequisites:
* An AWS account with configured credentials.
* Amazon Quick with an Author or higher subscription.
* Access to Amazon Bedrock with Anthropic models enabled.
* Python 3.10+ and a command-line environment with the AWS SDK.
* A running Docker daemon.

## 💡 Why it matters

Using this pattern promotes reusability and avoids the duplication of AI tools. Customers can leverage products within Amazon Quick chat agents and workflows without the need to build custom connectors for every unique use case. By deploying MCP servers on AgentCore Runtime, developers gain access to built-in observability, bidirectional streaming, and evaluation tools.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/07/07/ML-20742-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/07/07/ML-20742-2.png)

#AWS #AmazonBedrock #MCP #AIAgents #CloudComputing

---

*Source: [Connect an AgentCore Runtime hosted MCP server to Amazon Quick | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/connect-an-agentcore-runtime-hosted-mcp-server-to-amazon-quick/)*
