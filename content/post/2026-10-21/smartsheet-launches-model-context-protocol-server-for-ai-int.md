---
title: "Smartsheet Launches Model Context Protocol Server for AI Integration"
slug: "smartsheet-launches-model-context-protocol-server-for-ai-integration"
description: "Smartsheet has launched a generally available Model Context Protocol (MCP) Server, enabling AI assistants to read, write, and manage Smartsheet data through a standardized protocol. This integration..."
date: 2026-10-21T12:01:55+05:30
tags: [Smartsheet, MCP, AI, Automation, Integration]
categories: ["AI", "AI Agents", "Productivity Software", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21001-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Smartsheet Launches Model Context Protocol Server for AI Integration

Smartsheet has launched a generally available Model Context Protocol (MCP) Server, enabling AI assistants to read, write, and manage Smartsheet data through a standardized protocol. This integration supports more than 40 tools for interacting with sheets, rows, columns, and automations.

## 🧩 How it works
The Smartsheet MCP Server provides structured context, including row relationships, column types, cell history, and comments, to AI clients. By using this protocol, the server produces token-efficient payloads rather than returning raw API data. The server utilizes Streamable HTTP transport and supports authentication via OAuth 2.0 or Personal Access Tokens.

## ⚙️ Key details
| Endpoint Region | URL |
| :--- | :--- |
| Commercial US | https://mcp.smartsheet.com |
| EU | https://mcp.smartsheet.eu |
| AU | https://mcp.smartsheet.au |

* **Client Compatibility**: Connects with agentic AI workspaces like Amazon Quick and the Kiro IDE.
* **Capabilities**: Users can update task statuses, create rows, and modify project structures using natural language.
* **Requirements**: Access requires a Smartsheet Business, Enterprise, or AWM plan and a Personal Access Token or OAuth credentials.

## 💡 Why it matters
The use of MCP allows Smartsheet to function as a central integration layer for AI agents. For example, Amazon Quick can query the server to surface project summaries, while Kiro developers can reference project specs and track dependencies directly within their coding workflow. Automated hooks allow for status updates, such as marking a row as 'Complete' when a code fix is committed.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21001-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-21001-2.png)

#Smartsheet #MCP #AI #Automation #Integration

---

*Source: [Work management context for AI agents with Smartsheet MCP on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/work-management-context-for-ai-agents-with-smartsheet-mcp-on-aws/)*
*Source: [From data to decisions: Conversational supply chain intelligence with Amazon Quick and Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/from-data-to-decisions-conversational-supply-chain-intelligence-with-amazon-quick-and-amazon-bedrock-agentcore/)*
