---
title: "New automated AI solution monitors dashboard content failures"
description: "A new automated solution now monitors dashboards and visually analyzes them using large language models (LLMs) on Amazon Bedrock. The system detects visual content failures and provides proactive..."
date: 2026-09-03T22:06:46+05:30
tags: [AWS, AmazonBedrock, ArtificialIntelligence, Monitoring, Serverless]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21432-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# New automated AI solution monitors dashboard content failures

A new automated solution now monitors dashboards and visually analyzes them using large language models (LLMs) on Amazon Bedrock. The system detects visual content failures and provides proactive alerts, significantly reducing the mean time to detection.

## 🧩 How it works

The solution utilizes a five-stage architecture built on serverless and managed AWS services:

* Visual checks are triggered hourly by Amazon EventBridge.
* AWS Lambda functions orchestrate headless browser sessions to render dashboard sections as a user would see them.
* The system analyzes these renderings using LLMs on Amazon Bedrock.
* A configuration registry in Amazon Redshift manages section identifiers, owner assignments, and scheduling.
* When a failure is detected, owners receive a Slack notification containing the section name, a screenshot, the AI confidence score, and a link to the dashboard.
* Weekly data refreshes trigger separate numeric validation cycles that produce human-readable reports.

## 💡 Why it matters

* Mean time to detection was reduced from up to 72 hours to less than 1 hour.
* The system successfully detected 802 content failure instances, including row-level data permission errors, filters skipping records, and rendering issues.
* Instrumentation indicates that fewer than 1 percent of these failures had a corresponding user report.
* The architecture scales to zero between validation cycles to keep costs proportional to usage.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21432-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/31/ML-21432-2.png)

#AWS #AmazonBedrock #ArtificialIntelligence #Monitoring #Serverless

---

*Source: [How an AWS team detects dashboard content failures at scale using Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-an-aws-team-detects-dashboard-content-failures-at-scale-using-amazon-bedrock/)*
