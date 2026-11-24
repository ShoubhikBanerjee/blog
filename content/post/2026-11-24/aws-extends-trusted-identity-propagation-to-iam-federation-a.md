---
title: "AWS extends Trusted Identity Propagation to IAM Federation and Roles Anywhere"
slug: "aws-extends-trusted-identity-propagation-to-iam-federation-and-roles-anywhere"
description: "AWS has extended Trusted Identity Propagation (TIP) to support IAM federation and AWS IAM Roles Anywhere, enabling customers to grant access and audit activity based on the specific user or workload..."
date: 2026-11-24T18:09:57+05:30
tags: [AWS, IAM, CloudSecurity, IdentityManagement, CloudTrail, DevSecOps]
categories: ["AI", "Cloud Security", "Identity Management", "DevOps", "Enterprise IT"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/05/13/AdobeStock_1376596821-1260x630.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# AWS extends Trusted Identity Propagation to IAM Federation and Roles Anywhere

AWS has extended Trusted Identity Propagation (TIP) to support IAM federation and AWS IAM Roles Anywhere, enabling customers to grant access and audit activity based on the specific user or workload behind an IAM role.

## 🔍 Overview

Trusted Identity Propagation (TIP) carries the identity of a user or workload with each AWS request. This allows users to grant permissions to that specific user or workload and trace its actions in AWS CloudTrail. Previously, TIP was available only for users accessing AWS through AWS IAM Identity Center. The new extension makes TIP work for users and workloads that federate directly into IAM roles or use X.509 certificates to obtain AWS credentials, while also simplifying TIP usage with IAM Identity Center.

## 🧩 How it works

TIP addresses the gap where access control decisions apply to the role rather than the user, and CloudTrail attributes each action to the role session. By attaching identity context from a trusted source to the role session at credential issuance, TIP provides a stable reference for the user or workload behind each request. This context is immutable for the lifetime of the session and can include optional claims, such as a risk score or a CI/CD workflow name.

The identity context propagates through supported downstream requests:
*   **Role Assumption:** When a TIP session assumes another role, AWS Security Token Service (AWS STS) carries the context into the new role session.
*   **Forward Access Sessions (FAS):** When an AWS service makes a downstream request on your behalf, FAS credentials carry the identity context.
*   **Outbound Federation:** With IAM outbound identity federation, the session can request a signed JSON Web Token (JWT) that carries identity context to an external service.

## ⚙️ Key details

AWS validates the source and attaches identity context through three primary paths:

| Path | Source of Identity Context | Trusted Source Type |
| :--- | :--- | :--- |
| IAM Federation | SAML assertion or OIDC token | External SAML or OIDC Identity Providers (IdP) |
| IAM Identity Center | Username received from identity source | IAM Identity Center |
| IAM Roles Anywhere | X.509 certificate | X.509 certificates |

TIP context propagates to a new role session only under specific boundary conditions:
*   The target role is in the account where the identity provider is configured.
*   The target role is in another account within the same AWS organization.

IAM policies evaluate this identity context to authorize requests, and AWS CloudTrail records it for auditing. For example, Amazon S3 bucket policies and AWS Lambda can utilize this context for access control and audit logging. The identity context is represented through context keys, including the `aws:OriginIdentity/*` namespace, which serves as the common namespace for identity information across all three paths.

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/figure-1-identity-context-flow-v12-3600x1820-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/figure-2-github-actions-audit-v2-3200x1800-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/figure-3-runtime-risk-access-v4-3200x1800-2.png)

#AWS #IAM #CloudSecurity #IdentityManagement #CloudTrail #DevSecOps

---

*Source: [Know the identity behind the role: Authorize and audit with trusted identity propagation | Amazon Web Services](https://aws.amazon.com/blogs/security/know-the-identity-behind-the-role-authorize-and-audit-with-trusted-identity-propagation/)*
