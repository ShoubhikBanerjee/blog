---
title: "DXC OASIS AI Platform Launches with Amazon Bedrock and Guardrails"
slug: "dxc-oasis-ai-platform-launches-with-amazon-bedrock-and-guardrails"
description: "DXC Technology launched DXC OASIS, a governed AI agent platform built on Amazon Bedrock, to support mission-critical systems for regulated organizations."
date: 2026-11-12T22:08:51+05:30
tags: [A, W, S, A, m, a, z, o, n, B, e, d, r, o, c, k, A, I, A, g, e, n, t, s, E, n, t, e, r, p, r, i, s, e, A, I]
categories: ["AI", "E", "n", "t", "e", "r", "p", "r", "i", "s", "e", "A", "I", ",", "A", "W", "S", "S", "e", "r", "v", "i", "c", "e", "s", ",", "A", "I", "A", "g", "e", "n", "t", "s", ",", "M", "a", "n", "a", "g", "e", "d", "S", "e", "r", "v", "i", "c", "e", "s"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/02/ML-21702-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# DXC OASIS AI Platform Launches with Amazon Bedrock and Guardrails

DXC Technology launched DXC OASIS, a governed AI agent platform built on Amazon Bedrock, to support mission-critical systems for regulated organizations.

## 🔍 Overview
DXC OASIS separates the question of which model from the question of how work gets done. The system consists of two layers:
*   **Governed model substrate:** Built on Amazon Bedrock.
*   **Trusted harness:** DXC’s own orchestration, governance, and assurance layer.

## 🧩 How it works
DXC OASIS runs on Amazon Elastic Kubernetes Service (Amazon EKS) in a private subnet. Engineers and operators access the system via Amazon Route 53 and an Application Load Balancer inside the customer’s Amazon Virtual Private Cloud (Amazon VPC).

A supervisor agent delegates tasks to capability agents that draw on a knowledge base, AWS Secrets Manager, Amazon EventBridge, and Amazon Simple Storage Service (Amazon S3). Every model call leaves the subnet through a VPC interface endpoint and AWS PrivateLink to reach Amazon Bedrock.

## ⚙️ Key details
*   **Model Access:** Through a single managed interface, DXC OASIS accesses multiple foundation models: Anthropic Claude, Amazon Nova, Meta Llama, and open-weight families.
*   **Security and Guardrails:** Amazon Bedrock Guardrails enforce content filtering, personally identifiable information (PII) redaction, and denied-topic policies uniformly across every model.
*   **Data Privacy:** Across every model, customer data stays within the AWS data boundary. Prompts and completions are not shared with third-party model providers and are not used to train the underlying foundation models.
*   **Observability:** AWS Identity and Access Management (AWS IAM), AWS Key Management Service (AWS KMS), TLS 1.2, Amazon CloudWatch, VPC Flow Logs, AWS CloudTrail, and OpenTelemetry provide security and observability across every layer.

## 🚀 Availability
DXC began building DXC OASIS as a prototype in early 2025. A cross-functional team reached general availability in March 2026. Since that time, DXC OASIS has reduced resolution time by 95% on average across 56 measured use cases. The system is scaling toward 130 customer environments on Amazon EKS with per-tenant namespaces and GitOps rollout.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ml-21702-arch.png)

#A #W #S #, # #A #m #a #z #o #n # #B #e #d #r #o #c #k #, # #A #I # #A #g #e #n #t #s #, # #E #n #t #e #r #p #r #i #s #e # #A #I

---

*Source: [How DXC Technology built a multi-model AI substrate on Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-dxc-technology-built-a-multi-model-ai-substrate-on-amazon-bedrock/)*
