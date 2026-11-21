---
title: "AWS Introduces GetScopedCredentials API to Safely Scope Down Temporary Security Credentials"
slug: "aws-introduces-getscopedcredentials-api-to-safely-scope-down-temporary-security-credentials"
description: "AWS has launched GetScopedCredentials, a new AWS Security Token Service (AWS STS) API that enables you to scope down the permissions of existing temporary security credentials. This feature is..."
date: 2026-11-21T12:13:14+05:30
tags: [AWS, Security, IAM, AIAgents, CloudSecurity]
categories: ["AI", "Cloud Security", "Identity and Access Management", "AI Agents"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/10/21/Lock-data.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Introduces GetScopedCredentials API to Safely Scope Down Temporary Security Credentials

AWS has launched GetScopedCredentials, a new AWS Security Token Service (AWS STS) API that enables you to scope down the permissions of existing temporary security credentials. This feature is designed to help secure workloads, such as AI agents, by ensuring they only have the minimum permissions needed to perform their tasks rather than the full permissions of the calling session.

## 🔍 Overview

GetScopedCredentials provides a programmatic way to generate narrower security credentials from those you already possess. You can assign each agent, sub-agent, or process its own credentials that carry reduced permissions, a shorter session duration, or both, while keeping the original caller’s AWS Identity and Access Management (IAM) identity.

Because GetScopedCredentials works by narrowing the credentials you already have, it acts as a building block that you can integrate directly into:
* Agent frameworks
* Continuous integration and deployment (CI/CD) pipelines
* Services that issue credentials to other components
* Custom applications

## 🧩 How it works

To call the API, you must have valid temporary security credentials and the necessary permissions to call GetScopedCredentials. You can make the call using the latest version of the AWS Command Line Interface (AWS CLI) or the AWS SDK for your programming language.

The technical specifications of the API include:
* **Input Credentials:** You can call the API with the temporary credentials you already use, including those from aws login, an Amazon Elastic Compute Cloud (Amazon EC2) instance profile, or an AWS Lambda function.
* **Scope Down Policy:** In each call, you pass a scope down policy (an inline policy representing the maximum permissions) of up to 2,048 characters.
* **Intersection of Permissions:** The resulting permissions are the intersection of the session's effective permissions and the scope down policy. This ensures that permissions can only be reduced, never expanded.
* **Session Duration:** You can request a shorter session duration, which cannot exceed the remaining duration of the calling session.
* **Chaining Calls:** You can call GetScopedCredentials again using the resulting scoped-down credentials to restrict permissions or reduce duration even further. This allows an orchestrating agent to give sub-agents narrower access than its own.

## 💡 Common Use Cases

GetScopedCredentials can be applied whenever a workload requires narrower access than the session that initiates it. Notable use cases include:

* **Limiting AI Agent Actions:** AI agents decide on actions at runtime based on prompts or tool output. By using GetScopedCredentials, you can restrict their actions to only what is required—such as read access to a single Amazon Simple Storage Service (Amazon S3) bucket—or explicitly strip away risky actions like deleting resources. Run your agents in sandbox environments, such as AWS Strands Box, to ensure they only access these restricted credentials.
* **Scoping Down Based on Runtime Context:** Some workloads run under a single IAM role but require different permissions based on authenticated requests. For example, a multi-tenant application with a single IAM role that serves files from different prefixes in one S3 bucket can use a trusted credential broker to call GetScopedCredentials. The broker obtains credentials restricted to only the specific tenant's prefix and passes them to the worker.
* **Just-in-Time Access:** Securing tasks based on runtime data learned only after the workload begins.

#AWS #Security #IAM #AIAgents #CloudSecurity

---

*Source: [Scope down permissions of existing sessions using AWS STS GetScopedCredentials | Amazon Web Services](https://aws.amazon.com/blogs/security/scope-down-permissions-of-existing-sessions-using-aws-sts-getscopedcredentials/)*
