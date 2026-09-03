---
title: "AWS Expands Amazon Bedrock AgentCore with AI-DLC Reference Implementations"
description: "Amazon Bedrock AgentCore, a service for building, connecting, and optimizing agents at scale with any framework or model, now powers two new reference implementations that demonstrate AI-DLC..."
date: 2026-09-03T22:06:46+05:30
tags: [AmazonBedrock, AgentCore, AIDLC, AIagents, DevOps, AWS]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21366-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Expands Amazon Bedrock AgentCore with AI-DLC Reference Implementations

Amazon Bedrock AgentCore, a service for building, connecting, and optimizing agents at scale with any framework or model, now powers two new reference implementations that demonstrate AI-DLC construction phase patterns. AI-DLC positions AI as a central collaborator across the software development lifecycle, handling routine execution while humans retain oversight of critical decisions.

## 🔍 Overview

The two reference implementations cover:

- Automated generation of Mermaid entity relationship diagrams from SQL schemas
- Automated code security analysis through a multi-agent architecture

Both implementations link to complete deployment instructions in their respective GitHub repositories.

## 🧩 How It Works

### Mermaid ER Diagram Generator

This AWS Samples project auto-generates Mermaid ER diagrams from SQL schema files using an agentic AI workflow on Amazon Bedrock AgentCore.

**Architecture components:**

| Component | Function |
|-----------|----------|
| S3 event trigger | SQL files uploaded to Amazon S3 trigger an AWS Lambda function that initiates the analysis workflow |
| Amazon Cognito | Provides OAuth2 machine-to-machine (M2M) authentication |
| AWS Systems Manager Parameter Store | Stores client credentials |
| AgentCore runtime | Containerized agent built with the Strands framework |
| AgentCore memory | Persistent session context with 90-day expiry, supports semantic search across previous analyses |
| Amazon S3 | Output storage for generated .mmd files under dedicated prefix with metadata tracking |

**Workflow:**

- SQL file is uploaded to Amazon S3 (manually or through CI/CD pipeline)
- Lambda trigger reads file content and authenticates through Cognito OAuth
- Trigger invokes AgentCore runtime agent with SQL content as payload
- Agent analyzes schema and identifies tables, columns, constraints, and foreign key relationships
- Agent generates complete Mermaid erDiagram
- Diagram is saved to Amazon S3 and analysis session is stored in AgentCore memory

**Key design decisions:**

- Chunked processing: Large SQL files split into manageable segments, analyzed independently, then consolidated
- Structured prompting: Systematic analysis prompt extracts tables, columns, data types, primary keys, and foreign key relationships before generating diagram syntax
- OpenTelemetry tracing: Every step instrumented with spans and attributes for observability into processing duration, chunk counts, and error attribution

The agent uses Claude Sonnet 4 through Amazon Bedrock to parse SQL DDL statements. It reads only schema metadata (tables, constraints, and foreign keys), never row data.

### Automated Code Security Analysis

The second implementation provides automated code security analysis through a multi-agent architecture that uses:

- AgentCore Gateway
- AgentCore memory
- External tool integrations

This system analyzes code pushed through CI/CD pipelines, producing security assessments, Common Vulnerabilities and Exposures (CVE) checks, and policy compliance reports that inform human decision-making.

## ⚙️ Key Details

Both systems share a common architectural foundation built on AgentCore, demonstrating how teams can compose AI-driven workflows from modular, manageable components.

The AI-DLC construction phase positions AI to:

- Propose architecture
- Generate implementation plans
- Produce code
- Create deployment artifacts

Team members provide clarification on technical decisions in real time.

## 🚀 Availability

The complete implementation for the Mermaid ER diagram generator is available in its GitHub repository. The automated code security analysis implementation is also available with complete deployment instructions.

## 💡 Why It Matters

Database teams managing evolving SQL schemas need current entity relationship documentation. Manual creation of ER diagrams is time-intensive and documentation frequently drifts from the actual schema. When schema changes land through pull requests, teams need updated diagrams without adding manual documentation steps to the development workflow.

For security, continuous code quality enforcement through multi-agent systems ensures that assessments, CVE checks, and policy compliance reports inform human decision-making rather than replacing it.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21366-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21366-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21366-3.jpeg)

#AmazonBedrock #AgentCore #AIDLC #AIagents #DevOps #AWS

---

*Source: [AI-driven development lifecycle using Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/ai-driven-development-lifecycle-using-amazon-bedrock-agentcore/)*
*Source: [Set up OpenAI ChatGPT Codex with LiteLLM on Amazon ECS and Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/set-up-openai-chatgpt-codex-with-litellm-on-amazon-ecs-and-amazon-bedrock/)*
*Source: [Best practices for building agentic automations with Amazon Quick Automate | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/best-practices-for-building-agentic-automations-with-amazon-quick-automate/)*
