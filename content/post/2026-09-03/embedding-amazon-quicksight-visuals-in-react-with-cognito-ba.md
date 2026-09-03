---
title: "Embedding Amazon QuickSight Visuals in React with Cognito‑Based Per‑User Access"
description: "This post demonstrates how to embed individual Amazon QuickSight visuals into a React application while enforcing per‑user authentication through Amazon Cognito."
date: 2026-09-03T22:06:46+05:30
tags: [AWS, QuickSight, React, Cognito, Embedding]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/27/ML-20784-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Embedding Amazon QuickSight Visuals in React with Cognito‑Based Per‑User Access

This post demonstrates how to embed individual Amazon QuickSight visuals into a React application while enforcing per‑user authentication through Amazon Cognito.

## 🔍 Overview
- **Amazon Quick** is the unified analytics service from AWS that combines business intelligence, advanced analytics, and enterprise search.
- **Amazon QuickSight** is the business‑intelligence engine within Amazon Quick that powers the embedded analytics experience.
- Embedding at the visual level, rather than full dashboards, gives granular control over layout and user experience.

## 🧩 How it works
- **Front‑end**: A React application served through Amazon CloudFront, which delivers static files stored in an Amazon S3 bucket.
- **Security edge**: AWS WAF sits in front of CloudFront to filter malicious requests.
- **Authentication layer**: Amazon Cognito User Pools handle sign‑in and issue JSON Web Tokens (JWTs) that are validated by the API tier.
- **API layer**: An Amazon API Gateway endpoint protected by a Cognito Authorizer routes authenticated calls to an AWS Lambda function.
- **Backend processing**: The Lambda function assumes a dedicated IAM role and calls the Amazon QuickSight `GenerateEmbedUrlForRegisteredUser` API to produce a time‑scoped embed URL for the requested visual.
- **Analytics layer**: Amazon QuickSight renders the individual visual inside the React app using the Embedding SDK running entirely in the browser.
- **Observability**: Amazon CloudWatch captures logs and metrics from the Lambda function throughout the process.

## ⚙️ Key details
- A dedicated identity layer bridges Amazon Cognito and Amazon QuickSight, enabling fine‑grained access governance for every embedded visual.
- The Lambda function generates scoped embed URLs quickly and handles first‑time user provisioning.
- Each embed URL remains valid for an extended period, reducing re‑authentication friction during sessions.
- Deployment can be performed rapidly with a single AWS CloudFormation stack.
- The QuickSight account must have the application’s CloudFront domain registered in the embedding allowlist; otherwise the browser blocks the embedded iframe.
- Every Cognito user who needs to view an embedded visual must also exist as a registered user in Amazon QuickSight.
- On each embed request, the Lambda function:
  1. Extracts the user’s email from the validated JWT.
  2. Calls `describe_user` to check for an existing QuickSight user.
  3. If a `ResourceNotFoundException` is raised, calls `register_user` to create the user as a **READER**, the least‑privileged role that supports visual embedding.
- This approach provisions new Cognito users in QuickSight automatically on first access, with no manual intervention.

## 🚀 Why it matters
- Provides per‑user access control for embedded analytics without building separate dashboards for each use case.
- Keeps the solution lightweight by embedding individual visuals rather than full dashboards.
- Enables rapid, repeatable deployments using standard AWS infrastructure as code.
- Centralizes authentication and authorization, reducing complexity that many tutorials skip.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/03/arch_diag.png)

#AWS #QuickSight #React #Cognito #Embedding

---

*Source: [Embed Quick Sight visuals using Cognito user authentication | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/embed-quick-sight-visuals-using-cognito-user-authentication/)*
