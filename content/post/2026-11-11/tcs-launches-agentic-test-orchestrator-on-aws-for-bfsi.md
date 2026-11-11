---
title: "TCS Launches Agentic Test Orchestrator on AWS for BFSI"
slug: "tcs-launches-agentic-test-orchestrator-on-aws-for-bfsi"
description: "Tata Consultancy Services (TCS) has introduced the Agentic Test Orchestrator, a multi-tenant SaaS solution designed to automate testing for Banking, Financial Services, and Insurance (BFSI) clients...."
date: 2026-11-11T12:17:01+05:30
tags: [A, I, A, g, e, n, t, s, A, W, S, T, e, s, t, A, u, t, o, m, a, t, i, o, n, B, F, S, I, M, u, l, t, i, T, e, n, a, n, t]
categories: ["AI", "A", "I", "A", "g", "e", "n", "t", "s", ",", "S", "o", "f", "t", "w", "a", "r", "e", "T", "e", "s", "t", "i", "n", "g", ",", "A", "W", "S", ",", "E", "n", "t", "e", "r", "p", "r", "i", "s", "e", "S", "o", "f", "t", "w", "a", "r", "e"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-20381-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# TCS Launches Agentic Test Orchestrator on AWS for BFSI

Tata Consultancy Services (TCS) has introduced the Agentic Test Orchestrator, a multi-tenant SaaS solution designed to automate testing for Banking, Financial Services, and Insurance (BFSI) clients. The platform addresses the bottleneck where slowest part of a release is rarely writing application code, but rather the testing process itself.

## 🔍 Overview

The Agentic Test Orchestrator decomposes testing into specialized tasks, where each task has its own agent, tools, validation rules, and context. A deterministic supervisor routes work, while an execution workflow controls retries, error classification, persistence, and reporting.

## 🧩 How it works

The platform accepts inputs from various sources to generate executable tests:

*   **Inputs:** Jira stories, business requirement documents (BRDs), Swagger specifications, uploaded documents, GitLab source folders, or captured UI flows.
*   **Generation:** From these inputs, the platform generates test scenarios, Gherkin feature files, and executable Java or Python tests.
*   **Execution:** It runs those tests on Amazon ECS, stores artifacts and results, and shows progress and reports in a per-tenant web application.

## ⚙️ Key Details

### AWS Services Used

| Service | Function |
| :--- | :--- |
| **Amazon Bedrock AgentCore** | Hosts the platform's specialized agents built with the Strands Agents SDK. It offers model choice, runtime scaling, and microVM isolation. |
| **Amazon EKS** | Runs the tenant web application. |
| **Amazon ECS** | Runs the generated tests. |
| **Amazon S3 & Amazon DynamoDB** | Store the results. |
| **Amazon CloudWatch** | Captures the logs. |
| **Security Services** | AWS WAF, Amazon Cognito, AWS KMS, and AWS Secrets Manager enforce per-tenant security and isolation. |

### Architecture

The solution is built on a shared control plane and tenant application planes:

*   **Shared Control Plane:** Provides the Amazon EKS cluster, container registry, administrative portal, tenant registry, onboarding automation, Amazon CloudFront distributions, and AWS WAF protection.
*   **Tenant Application Plane:** Each tenant receives its own Kubernetes namespace, Amazon Cognito user pool, AWS KMS key, Amazon S3 bucket, Amazon DynamoDB tables, and Amazon Bedrock Knowledge Bases.

### Onboarding Process

The administrative API writes a pending tenant record, emits an event through Amazon EventBridge, and starts an AWS CodeBuild project that deploys the tenant infrastructure with AWS Cloud Development Kit (AWS CDK).

## 💡 Why it matters

For BFSI clients, the platform is designed to meet strict requirements:

*   **Context:** Every test must be grounded in project-specific context rather than generic prompts.
*   **Coverage:** It covers both API and browser-based UI testing to match how BFSI applications are built.
*   **Security:** Every tenant’s data and knowledge store must be isolated.
*   **Repeatability:** It provides a repeatable path from requirement ingestion to test evidence and reporting.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-20381-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-20381-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/06/ML-20381-3.jpg)

#A #I # #A #g #e #n #t #s #, # #A #W #S #, # #T #e #s #t # #A #u #t #o #m #a #t #i #o #n #, # #B #F #S #I #, # #M #u #l #t #i #- #T #e #n #a #n #t

---

*Source: [How TCS built an agentic test orchestrator with Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-tcs-built-an-agentic-test-orchestrator-with-amazon-bedrock-agentcore/)*
