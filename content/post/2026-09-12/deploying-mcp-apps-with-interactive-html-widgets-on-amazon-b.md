---
title: "Deploying MCP Apps with Interactive HTML Widgets on Amazon Bedrock AgentCore"
slug: "deploying-mcp-apps-with-interactive-html-widgets-on-amazon-bedrock-agentcore"
description: "Amazon Bedrock AgentCore now enables the deployment of MCP Apps, which extend the Model Context Protocol (MCP) by rendering interactive HTML widgets directly inside AI hosts."
date: 2026-09-12T12:03:17+05:30
tags: [AmazonBedrock, MCP, AIagents, AWS]
categories: ["AI", "AI Agents", "Cloud Computing", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-20314-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Deploying MCP Apps with Interactive HTML Widgets on Amazon Bedrock AgentCore

Amazon Bedrock AgentCore now enables the deployment of MCP Apps, which extend the Model Context Protocol (MCP) by rendering interactive HTML widgets directly inside AI hosts.

## 🔍 Overview

Amazon Bedrock AgentCore is a platform designed to build, connect, and optimize agents at scale using any model or framework. It provides two primary capabilities to support MCP Apps:

| Capability | Function |
| :--- | :--- |
| AgentCore runtime | Provides a secure, serverless, session-isolated host with native MCP support. |
| AgentCore Gateway | Exposes the runtime through a single secure endpoint reachable by MCP Apps-compatible hosts. |

## 🧩 How it works

To demonstrate these capabilities, a sample application called Unicorn Rentals was deployed as an MCP App. The workflow operates as follows:

* **Request Initiation**: An AI host translates a request into an MCP tools/call message (e.g., `list_unicorns`) and sends it to the AgentCore Gateway endpoint.
* **Security**: AWS WAF screens the request using managed rules and an IP allowlist before it reaches the gateway.
* **Execution**: The AgentCore Gateway uses its AWS Identity and Access Management (IAM) execution role to invoke the AgentCore runtime.
* **Business Logic**: The MCP App delegates operations to a dedicated AWS Lambda function, which executes logic against Amazon DynamoDB for persistence.
* **Response**: The MCP App wraps the result in MCP format and returns it to the AI host. The host then sends an MCP resources/read request for the associated URI.

## ⚙️ Key details

The Unicorn Rentals app utilizes specific MCP tools and resources to manage bookings:

* **MCP Tools**: `list_unicorns`, `book_unicorn`, `view_bookings`, and `return_unicorn`.
* **MCP Resources**: `unicorn-list` and `booking-confirmation`, which supply the HTML for the interactive widgets.
* **Capabilities**: The app can browse unicorns, book rentals, view active bookings, and return unicorns. It can report booking IDs, dates, hourly rates, and calculate total costs based on duration.

https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-20314-5.png

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/09/ML-20314-5.png)

#AmazonBedrock #MCP #AIagents #AWS

---

*Source: [Build interactive MCP Apps using Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-interactive-mcp-apps-using-amazon-bedrock-agentcore/)*
