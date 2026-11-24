---
title: "AWS Simplifies WAF Pricing with Three-Dimensional Model"
slug: "aws-simplifies-waf-pricing-with-three-dimensional-model"
description: "Starting today, AWS WAF pricing is easier to predict. Your bill is now based on three dimensions: the resources you protect, the traffic AWS WAF inspects, and the level of protection you apply to..."
date: 2026-11-24T12:08:32+05:30
tags: [AWS, WAF, CloudSecurity, Pricing]
categories: ["AI", "Cloud Security", "Web Application Firewalls", "Pricing Models", "Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/23/WAF-pricing-hero-image-v2-1260x630.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Simplifies WAF Pricing with Three-Dimensional Model

## 📊 Overview
Starting today, AWS WAF pricing is easier to predict. Your bill is now based on three dimensions: the resources you protect, the traffic AWS WAF inspects, and the level of protection you apply to that traffic. For new or smaller workloads, the Free plan of CloudFront flat-rate pricing plans is another way to start. If your application serves fewer than 1 million requests per month, the Free plan costs $0 per month for each CloudFront distribution. It includes AWS WAF protection against common web threats, DDoS protection, and the CloudFront CDN, with no overage charges.

## ⚙️ Key Details
- Adding a protection (such as a rule, Bot Control, or Anti-DDoS rule group) no longer adds a subscription or a separate per-request charge. Those requests bill at the base request rate.
- Capacity no longer affects your rate. Each protection pack (web ACL) now includes up to 2,500 web ACL capacity units (WCUs), up from 1,500, and going past your included capacity does not raise what you pay per request.
- The premium request fee applies only to the traffic you choose to send through advanced protections.
- You can estimate costs before writing a first rule, and those estimates hold even as your rules change.
- Security rules change often. Adding, reordering, or removing rules does not change your rate.
- For AWS Shield Advanced subscribers, nothing changes. Your Shield Advanced subscription, its price, and your included AWS WAF entitlement stay the same.
- Customers on a CloudFront flat-rate pricing plan also see no change.

## 💰 How Costs Are Calculated
AWS WAF bills three fees:

| Fee Type | Description |
|----------|-------------|
| Resource Fee | Hourly charge for each resource associated with a protection pack (e.g., CloudFront distributions, Application Load Balancers, Amazon API Gateway APIs). |
| Base Request Fee | Applies to each request AWS WAF inspects. |
| Premium Request Fee | Applies on top of the base request fee, to requests evaluated by advanced protections like Bot Control, Fraud Control, API Security, and AI Security. |

Both API Security and AI Security use the same premium request fee, with no separate subscription or rate. Requests evaluated by one or more advanced protections are billed $5.60 per million: the $0.60 base request fee plus the $5.00 premium request fee. AWS WAF charges the premium request fee once per request, however many advanced protections evaluate it. A request blocked before reaching an advanced protection pays only the base request fee.

## 🚀 Availability and Transition
- Existing AWS WAF customers move to the new pricing on February 1, 2027. Until then, they keep their current pricing and don’t need to do anything at launch.
- If you hold an AWS WAF private pricing agreement, it stays in force until it expires.
- The new pricing includes the Security analytics dashboard, which shows full traffic metrics for your protected applications over a rolling 21-day window at no additional cost.

## 💡 Example: Cost Estimation
Here’s a worked example from the AWS WAF pricing page:

Example 1: One protected resource (Application Load Balancer) serving 20 million requests per month.

- Resource fee: 1 resource × $0.01 per hour × 730 hours = $7.30
- Base request fee: 20 million × $0.60 per million = $12.00
- Total: $19.30 per month

For more pricing details and examples, visit the AWS WAF pricing page. If you have questions about how the new pricing applies to your account, contact your AWS account team or open a Support case.

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/19/waf-pricing-scenarios-Figure-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/19/waf-old-vs-new-pricing-flow-Figure-1.png)

#AWS #WAF #CloudSecurity #Pricing

---

*Source: [Introducing AWS WAF simplified pricing | Amazon Web Services](https://aws.amazon.com/blogs/security/introducing-aws-waf-simplified-pricing/)*
