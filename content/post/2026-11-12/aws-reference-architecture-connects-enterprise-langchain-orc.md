---
title: "AWS Reference Architecture Connects Enterprise LangChain Orchestrator to SaaS Compliance Agent via A2A"
slug: "aws-reference-architecture-connects-enterprise-langchain-orchestrator-to-saas-compliance-agent-via-a2a"
description: "A reference implementation on AWS demonstrates how the Agent-to-Agent (A2A) protocol lets an enterprise LangChain orchestrator work with a Strands Agents‑based compliance SaaS agent across separate..."
date: 2026-11-12T22:08:51+05:30
tags: [AWS, A2A, LangChain, Bedrock]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Agent Systems", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21127-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Reference Architecture Connects Enterprise LangChain Orchestrator to SaaS Compliance Agent via A2A

A reference implementation on AWS demonstrates how the Agent-to-Agent (A2A) protocol lets an enterprise LangChain orchestrator work with a Strands Agents‑based compliance SaaS agent across separate AWS accounts.

## 🔍 Overview
- Agents in multi‑agent systems that span organizational boundaries often need to collaborate in a composable, interoperable way, with agents that other organizations build and run.
- The Agent-to-Agent (A2A) protocol addresses this constraint.
- The A2A protocol is now a Linux Foundation project, and AWS is among the organizations that support it.

## 🧩 How it works
- Three agents run in two AWS accounts, one for the enterprise and one for the SaaS provider.
- Each account has its own Amazon Cognito user pool, so each side authenticates with its own identity provider.
- During onboarding the enterprise and the SaaS provider exchange only public values, such as identity provider URLs, client IDs, scopes, and endpoint URLs.
- The enterprise app gets an access token from the enterprise’s Amazon Cognito user pool.
- The app sends a question over HTTPS to the user API in Amazon API Gateway, then polls for the answer.
- Amazon API Gateway forwards the request privately, through a VPC link and an internal Network Load Balancer, to the Enterprise Orchestrator, a LangChain agent.
- When its model decides that the question needs a compliance scan, the orchestrator gets its own token from the enterprise user pool, using a client secret stored in AWS Secrets Manager.
- The orchestrator sends an A2A request to the compliance SaaS agent on Amazon Bedrock AgentCore runtime, using the skill it read from the agent’s Agent Card at startup.
- The compliance agent checks the enterprise context agent’s Agent Card at the callback URL registered at onboarding, then gets a token from the SaaS provider’s own pool.
- The compliance agent calls back to the enterprise context agent for account metadata, finishes its scan, and returns the answer to the orchestrator and then to the app.
- Both enterprise agents run on Amazon ECS with AWS Fargate in private subnets of an Amazon VPC, with no public IP addresses.
- The SaaS agent reaches the context agent through an API Gateway partner API that accepts only the SaaS provider’s callback token.

## ⚙️ Key details
- Deployed agent uses the official a2a-sdk (AgentCard, AgentExecutor, and spec-conformant JSON-RPC routes), pinned to a2a-sdk[http-server]==1.2.2.
- At startup the orchestrator fetches the SaaS agent’s Agent Card from its well‑known URL and creates a LangChain tool for each skill described on the card.

| Agent | Runtime / Framework | Model | Role |
|------|----------------------|-------|------|
| Enterprise Orchestrator | LangChain on Amazon ECS (Fargate) | Anthropic Claude Sonnet 4.6 (Bedrock) | Receives user queries, decides when to invoke compliance scan |
| Enterprise Context Agent | LangChain on Amazon ECS (Fargate) | Amazon Nova Lite (Bedrock) | Provides internal account metadata, policy rules, data classification |
| Compliance SaaS Agent | Strands Agents on Amazon Bedrock AgentCore | – | Performs compliance scan and returns results |

## 🚀 Availability
- The protocol uses existing authentication standards such as OAuth 2.0 and OpenID Connect (OIDC) for cross‑boundary security, and is designed to work across A2A‑compatible frameworks.
- Independent software vendors (ISVs) can build composable, interoperable agents that work with the A2A‑compatible frameworks their customers already use.

## 💡 Why it matters
- Neither side depends on the other’s framework or SDK, and the two sides share no secrets.
- The architecture shows how organizations can keep agents isolated in private subnets while still enabling secure, standards‑based cross‑account collaboration.

#AWS #A2A #LangChain #Bedrock

---

*Source: [Build composable, interoperable multi-agent systems with A2A on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-composable-interoperable-multi-agent-systems-with-a2a-on-aws/)*
