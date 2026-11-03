---
title: "Circle K Deploys Automated Incident Triage Using Amazon Bedrock"
slug: "circle-k-deploys-automated-incident-triage-using-amazon-bedrock"
description: "This post was co‑written with Marek Klatowicz, Cloud DevOps Engineer at Circle K."
date: 2026-11-03T06:04:06+05:30
tags: [AI, IncidentTriage, AmazonBedrock, DevOps]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "DevOps", "Incident Management"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21514-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Circle K Deploys Automated Incident Triage Using Amazon Bedrock

This post was co‑written with Marek Klatowicz, Cloud DevOps Engineer at Circle K.

## 🔍 Overview
Circle K runs a cloud‑native infrastructure on AWS that powers point‑of‑sale systems, loyalty applications, and electric‑vehicle charging across more than 17,200 convenience and fuel retail stores in 27 countries. The DevOps team monitors this environment with Grafana and receives alerts for container restarts, error‑rate spikes, latency issues, and failed deployments.

## ⚠️ Manual Triage Pain
When an alert fires, engineers typically spend 45–60 minutes repeating the same steps:
- Review recent logs in Amazon CloudWatch.
- Examine application traces in Amazon OpenSearch Service.
- Check Amazon ECS task status.
- Cross‑reference symptoms with internal runbooks stored in GitHub.
The depth and speed of triage vary with each on‑call engineer’s familiarity with the affected service.

## 🤖 Solution: Agentic AI Triage with Amazon Bedrock
Circle K built an automated triage system that uses Amazon Bedrock, a fully managed service that makes foundation models available through a single API. The system employs an agentic AI architecture that investigates each incident autonomously and delivers a structured summary to Slack within minutes of an alert firing.

### Key Bedrock Benefits
- Single API access to multiple foundation models; models can be swapped without code changes.
- Native integration with existing AWS IAM, VPC, and logging configurations.
- Built‑in orchestration that lets agents call AWS APIs, query databases, and retrieve documents.
- Bedrock Knowledge Bases provide managed Retrieval‑Augmented Generation, handling ingestion and retrieval of internal product cards without a separate vector database.
- Customer data is not shared with model providers nor used to train foundation models, satisfying Circle K’s security requirements.

## 🏗️ Architecture
The end‑to‑end flow starts with a Grafana alert and proceeds through AWS services as follows:

| Component | Role |
|---|---|
| Grafana alert | Publishes a notification to Amazon SNS |
| Amazon SNS | Forwards the notification to an Amazon SQS queue |
| Amazon SQS | Holds the alert payload for processing |
| AWS Lambda | Polls the queue, extracts the payload, and invokes an Amazon Bedrock Flow |
| Amazon Bedrock Flow | Orchestrates two parallel agents that perform log queries, health checks, and runbook lookups |
| Slack | Receives the structured incident summary |

## 📊 Impact
Since deployment, Circle K’s mean triage time has dropped to under 15 minutes—a 67–75 percent reduction according to internal incident‑response metrics. On‑call engineers now receive actionable context instead of raw alerts, allowing immediate remediation.

## 🚀 Availability
Amazon Bedrock model availability varies by AWS Region; refer to the "Supported models by AWS Region" documentation for details.

## 💡 Why It Matters
- Consistent, fast triage reduces mean time to resolution.
- Reduces manual effort and reliance on individual engineer expertise.
- Meets strict security requirements by keeping sensitive operational data within the customer’s AWS account.
- Eliminates the overhead of self‑hosting foundation models, prompting, versioning, and tool orchestration.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-21514-first-arch-final.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-21514-second-arch-final.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21514-3.jpg)

#AI #IncidentTriage #AmazonBedrock #DevOps

---

*Source: [How Circle K accelerated DevOps incident triage to under 15 minutes with Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-circle-k-accelerated-devops-incident-triage-to-under-15-minutes-with-amazon-bedrock/)*
