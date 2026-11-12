---
title: "Amazon Bedrock AgentCore adds Web Search API"
slug: "amazon-bedrock-agentcore-adds-web-search-api"
description: "Amazon announced a new Web Search API on Bedrock AgentCore that lets developers retrieve ranked web results with a single API call."
date: 2026-11-12T22:08:51+05:30
tags: [AmazonWebServices, Bedrock, WebSearchAPI]
categories: ["AI", "Cloud Computing", "AI Agents", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/11/ML-22165-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore adds Web Search API

Amazon announced a new Web Search API on Bedrock AgentCore that lets developers retrieve ranked web results with a single API call.

## 🔍 Overview
- The Web Search API returns ranked results from an Amazon‑operated web index.
- Each result includes a text extract and, when available, the page title, URL, and publication time.
- The API can be invoked via AWS SDKs or the AWS Command Line Interface (AWS CLI).

## 🧩 How it works
- The API is exposed as the **InvokeWebSearch** operation on the **bedrock-agentcore** data plane.
- It runs on the same search infrastructure that powers Alexa+, Kiro, Quick, and other Amazon products.
- Calls are signed with AWS Signature Version 4 (SigV4) using standard IAM credentials; no separate API key is required.
- The recommended integration point for most agentic workloads is the AgentCore Gateway, which provides a single Model Context Protocol (MCP) endpoint that combines web search with other tools.
- When executed from a VPC, the call can travel through an interface VPC endpoint.

## ⚙️ Key details
- **Result limits**: Request between 1 and 25 results per query; if `maxResults` is omitted, up to 25 results are returned.
- **Result content**: Each result contains a text extract and, when available, title, URL, and publication time.
- **Search query**: `searchQuery` may be up to 200 characters.
- **Domain filtering**: Include or exclude up to 100 domain names; a root domain also matches its subdomains.
- **Publication‑time filtering**: Use `publishedAfter` and `publishedBefore` (RFC 3339 UTC) to restrict results; both bounds are inclusive.
- **Permissions**: The caller must have the IAM permission `bedrock-agentcore:InvokeWebSearch` on the managed web search tool. One IAM policy covers both the gateway and direct API routes.
- **Execution context**: If code runs on AWS Lambda, Amazon ECS, Amazon EC2, or Amazon EKS, the execution role supplies credentials automatically.

| Component   | Description |
|-------------|-------------|
| Operation   | InvokeWebSearch on the bedrock-agentcore data plane |
| Endpoint    | AgentCore Gateway MCP endpoint (recommended) |
| Permission  | `bedrock-agentcore:InvokeWebSearch` IAM permission |

## 🚀 Availability
- The API can be called from any environment that can use the AWS SDKs or AWS CLI.
- Calls are signed with the same IAM credentials used for other AWS services.
- When run inside a VPC, an interface VPC endpoint can be used for private connectivity.
- Execution roles for Lambda, ECS, EC2, and EKS automatically provide the necessary credentials.

## 💡 Why it matters
- Provides a direct, compliant web‑search capability for agents without managing external API keys.
- Leverages Amazon’s own high‑quality search infrastructure, ensuring consistent quality and compliance.
- Integrates seamlessly with other AgentCore tools such as AgentCore Browser through the same endpoint.
- Enables developers to scope searches to trusted domains and recent publications, improving relevance for AI‑driven applications.

#AmazonWebServices #Bedrock #WebSearchAPI

---

*Source: [Introducing the Web Search API on Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-the-web-search-api-on-amazon-bedrock-agentcore/)*
