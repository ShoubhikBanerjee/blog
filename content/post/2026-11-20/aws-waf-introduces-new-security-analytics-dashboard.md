---
title: "AWS WAF Introduces New Security Analytics Dashboard"
slug: "aws-waf-introduces-new-security-analytics-dashboard"
description: "AWS has introduced a new security analytics dashboard for AWS WAF, providing a single global page to investigate traffic across all protection packs (web ACLs), Regional resources, and Amazon..."
date: 2026-11-20T18:09:02+05:30
tags: [AWS, WAF, WebSecurity, CloudSecurity, DataAnalytics]
categories: ["AI", "Cloud Security", "Web Application Security", "AWS", "Data Analytics"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/05/05/aws_logo.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# AWS WAF Introduces New Security Analytics Dashboard

AWS has introduced a new security analytics dashboard for AWS WAF, providing a single global page to investigate traffic across all protection packs (web ACLs), Regional resources, and Amazon CloudFront distributions. This update builds on the 2024 traffic overview dashboard by offering a consolidated view that helps users act on findings faster.

## 🔍 Overview
The new dashboard is designed to help users investigate and contain threats faster while reducing false positives that block real customers. Key aspects of the update include:
- A single global page for investigating traffic across all protection packs (web ACLs).
- Coverage of Regional resources and Amazon CloudFront distributions.
- No need to build or maintain a custom log analytics pipeline.
- Built on full-fidelity request data rather than samples.
- Two primary use cases demonstrated: investigating a traffic spike and tuning rules to reduce false positives.

## 🧩 How It Works
To access the dashboard, users navigate to the AWS WAF console and select "Security analytics" in the navigation pane. The interface allows users to narrow the view to specific protection packs and set time ranges. 

- **Global View**: The dashboard displays request data across all protection packs in the account. Selecting "All protection packs" shows a comprehensive view.
- **Traffic Breakdown**: The top of the page shows total requests split by action: Allow, Block, CAPTCHA, and Challenge.
- **Charts and Widgets**: The "Requests chart" visualizes traffic changes over time, while widgets below display top values for specific dimensions. Users can split the Requests chart by dimensions such as Host, Rule triggered, Country, or JA4.
- **Host Grouping**: Grouping or filtering by Host identifies which domains are under attack or experiencing spikes, even when a single protection pack protects multiple domains or a domain spans several protection packs.
- **Labels and Detections**: AWS Managed Rules add labels (e.g., Bot Control categories, verification status, and signals like `non_browser_user_agent`). Users can also create custom labels. Because labels are recorded even when a rule is set to count-only, filtering by a label shows what a rule detected across all protection packs without changing how traffic is handled.
- **Filters and Actions**: Filters apply to the entire dashboard, updating the action split, Requests chart, widgets, and request list. Users can select any value in a widget to focus on it, remove it, or block it.
- **Request Details**: For individual requests, the dashboard displays HTTP fields such as host, path, headers, user agent, and JA4 fingerprint. It also shows which detections and labels matched and whether each action was enforced or only counted.

## ⚙️ Key Details
Previously, accessing this level of detail required working from a limited sample of requests or setting up and querying custom AWS WAF logs. The new dashboard makes this data available directly. Additionally, the current dashboard view is saved in the user's browser.

## 💡 Why It Matters
This tool allows security teams to move from reactive log analysis to proactive investigation and containment. By providing full-fidelity data without the overhead of maintaining custom pipelines, organizations can more effectively tune their rules to minimize false positives and protect their infrastructure.

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/18/Figure2-RequestsGroupedbyRuleTriggered.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/18/Figure5-Reqestdetails.png)

#AWS #WAF #WebSecurity #CloudSecurity #DataAnalytics

---

*Source: [Introducing the new AWS WAF security analytics dashboard | Amazon Web Services](https://aws.amazon.com/blogs/security/introducing-the-new-aws-waf-security-analytics-dashboard/)*
