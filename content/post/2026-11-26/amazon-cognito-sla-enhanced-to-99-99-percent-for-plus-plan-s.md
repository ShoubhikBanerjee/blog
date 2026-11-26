---
title: "Amazon Cognito SLA Enhanced to 99.99 Percent for Plus Plan Starting November 2026"
slug: "amazon-cognito-sla-enhanced-to-99-99-percent-for-plus-plan-starting-november-2026"
description: "Amazon Cognito's Service Level Agreement (SLA) for user pools on the Plus feature plan is increasing from 99.9 percent to 99.99 percent, effective November 1, 2026. This enhancement ensures tighter..."
date: 2026-11-26T12:19:42+05:30
tags: [AWS, Cognito, SLA, IAM, HighAvailability, UserPools]
categories: ["AI", "Web Development", "Cloud Computing", "Security", "DevOps"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/23/AWS-Security-Blog-99.99_-Hero-Image.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Cognito SLA Enhanced to 99.99 Percent for Plus Plan Starting November 2026

Amazon Cognito's Service Level Agreement (SLA) for user pools on the Plus feature plan is increasing from 99.9 percent to 99.99 percent, effective November 1, 2026. This enhancement ensures tighter uptime guarantees for applications that rely on Cognito's sign-in and access management capabilities.

## 📌 Why It Matters

Sign-in is the front door to your application. If your customer identity and access management (CIAM) layer is unavailable, users can't sign in or refresh their sessions, preventing access to the rest of your application. The application's availability directly depends on the availability of your identity layer.

Many customers use Amazon Cognito for applications with strict availability requirements, such as patient portals and retail checkout flows. They need the services they build on to support high availability. The 99.99 percent SLA provides 10 times better reliability than the previous 99.9 percent commitment.

## ⚙️ Key Details

The SLA improvement applies specifically to user pools on the Plus feature plan. User pools on Essentials and Lite feature plans will continue with the 99.9 percent Service Commitment.

- **99.99 Percent SLA (Plus plan):** Reduces allowable monthly downtime from ~43 minutes to ~4.3 minutes in a 30-day month.
- **99.9 Percent SLA (Essentials and Lite plans):** Remains unchanged.
- Existing Plus plan user pools automatically receive the new commitment; no action is required.

The SLA measures availability per AWS Region, calculating the Monthly Uptime Percentage based on 5-minute intervals and excluding HTTP 500 or 503 errors. Intervals with no requests count as 100 percent available.

## 🚀 Availability Performance

Historical data shows strong performance relative to these commitments.

- Availability was at or above 99.99 percent in 10 of the 12 months.
- It was below 99.99 percent in January (99.988 percent) and March (99.979 percent), but stayed above the previous 99.9 percent commitment in both months and reached 99.99 percent the following month.

## 🛠️ Switching to Plus

Organizations can switch user pools to the Plus feature plan to qualify for the improved SLA.

This can be done via:

- AWS Management Console: Navigate to User Pools, select your pool, go to Settings > Feature Plans tab, and choose "Switch to Plus."
- AWS CLI: Using the Update-user-pool command or UpdateUserPool API operation. Note that unspecified parameters reset to default values.

Before switching, users should compare features and costs in the user pool feature plans and Amazon Cognito pricing documentation.

#AWS #Cognito #SLA #IAM #HighAvailability #UserPools

---

*Source: [Planning for 99.99 percent availability with the Amazon Cognito Plus feature plan | Amazon Web Services](https://aws.amazon.com/blogs/security/planning-for-99-99-percent-availability-with-the-amazon-cognito-plus-feature-plan/)*
