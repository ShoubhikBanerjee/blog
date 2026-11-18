---
title: "LoanPro Deploys Multi-Agent AI Assistant with AWS and AllCloud"
slug: "loanpro-deploys-multi-agent-ai-assistant-with-aws-and-allcloud"
description: "LoanPro has launched a multi-agent AI assistant built with AWS Partner AllCloud and the AWS Generative AI Innovation Center that provides servicing agents with synthesized borrower context and..."
date: 2026-11-18T06:16:59+05:30
tags: []
categories: ["AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/11/ML-21891-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# LoanPro Deploys Multi-Agent AI Assistant with AWS and AllCloud

LoanPro has launched a multi-agent AI assistant built with AWS Partner AllCloud and the AWS Generative AI Innovation Center that provides servicing agents with synthesized borrower context and actionable next-step recommendations. The system uses Amazon Bedrock with Anthropic’s Claude models and shows early results of up to 15 percent reduction in customer call times.

## 📊 Overview
LoanPro is the operating system for modern lenders, an API-first lending and credit platform that automates the entire loan lifecycle from origination to payoff. Founded in 2015, the platform serves over 450 lenders across fintechs, banks, credit unions, and corporates, with loans managed on its platform reaching about 31 percent of US households. It is not a lender but the system of record that lenders run on.

## 🧩 How it works
The AI assistant was designed and built using the Strands Agents SDK and orchestrated with Amazon Bedrock AgentCore. A user request enters through LoanPro API v2 on Amazon API Gateway, then an AWS Lambda handler places it on an Amazon Simple Queue Service (Amazon SQS) queue. The Agent Interceptor Lambda function invokes the Loan Summary Agent, which runs on Amazon Bedrock AgentCore runtime and uses Anthropic’s Claude models.

The agent reaches its tools through a Model Context Protocol (MCP) server on Amazon Bedrock AgentCore Gateway, which finds the right tool in a catalog registered in AWS Systems Manager Parameter Store. The Loan Summary Tool Lambda function validates the caller’s signature against LoanPro’s SSO service and retrieves account data from LoanPro’s loan management system running on Amazon EC2 behind a Network Load Balancer.

## ⚙️ Key details
The system uses multiple Claude model variants:

- Claude Sonnet 5.5
- Claude Haiku 5.5
- Claude Opus 5.5

All models run on Amazon Bedrock. Model availability varies by AWS Region.

The architecture includes:

- Amazon Bedrock for foundation model access through a single API
- Amazon Bedrock AgentCore for managed agent runtime and orchestration
- Strands Agents SDK for agent logic and tool use
- Role-based access controls validating user permissions and compliance controls
- Audit trail logging every action

## 💡 Why it matters
By choosing managed services over building agent runtime and model access in-house, the team gained flexibility to adopt new models without managing separate endpoints. Amazon Bedrock AgentCore removes the operational overhead of running agents in production, while the multi-agent approach allows specialized agents to handle focused tasks that can be evaluated and improved independently.

---

*Source: [How LoanPro built an agentic AI loan servicing assistant with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-loanpro-built-an-agentic-ai-loan-servicing-assistant-with-amazon-bedrock-agentcore/)*
