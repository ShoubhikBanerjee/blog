---
title: "Amazon Quick adds Smart Approvals for automated action review"
slug: "amazon-quick-adds-smart-approvals-for-automated-action-review"
description: "Smart Approvals in Amazon Quick addresses this challenge by reviewing eligible actions within your existing controls."
date: 2026-11-05T22:04:09+05:30
tags: [AmazonQuick, SmartApprovals, AI, CloudTrail, Automation]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Security", "Enterprise Software"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22232-featured-image-1.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Quick adds Smart Approvals for automated action review

Smart Approvals in Amazon Quick addresses this challenge by reviewing eligible actions within your existing controls.

## 🔍 Overview
- Smart Approvals in Amazon Quick reviews eligible actions within your existing controls.

## 🧩 How it Works
- It evaluates each proposed action against the user’s request and either approves it automatically or returns it to the user for review.
- Quick evaluates each proposed action against Custom Permissions, Quick Guardrails, connector action permissions, and the user’s settings before automated review.
- With Smart Approvals enabled, an action is eligible only when the user’s setting is “Ask each time” and no other control requires human approval.
- Smart Approvals uses a separate model, the classifier, to evaluate eligible actions against the user’s request and a bounded view of the conversation.
- It can consult the user’s knowledge graph, which contains people and working relationships drawn from connected sources. This lookup stays within your Quick account.
- Quick doesn’t use the content the classifier reviews, including knowledge graph data, to train models or improve the service.
- Quick instructs both the agent and classifier to treat that content as information, not instructions.
- Each automatic approval is single‑use, applies only to the exact action and parameters reviewed, and grants no ongoing permission.
- Quick labels automatic approvals in the conversation.

## ⚙️ Permissions & Controls
- Administrators use Custom Permissions to determine who can use Smart Approvals.
- Connector action permissions, configured when a connector is created, can require human approval for specific actions.
- It’s on by default, but profiles with deny‑by‑default enabled must explicitly allow it.
- Users can also turn Smart Approvals off for themselves. That choice applies across conversations and scheduled runs.
- When it’s off, actions otherwise eligible for automated review require the user’s approval, and no account‑level setting can turn it back on for them.

## 📜 Auditing & Logging
- The Quick permission service records permission updates associated with Smart Approvals in AWS CloudTrail in your account.
- Each event identifies the user, connector, action, and time, and marks the request as associated with Smart Approvals.
- Quick also records permission‑check verdicts, including denials from connector action permissions, and changes to a user’s Smart Approvals setting.
- Investigators can correlate these events by user and time with other Quick activity in CloudTrail and logs delivered through Amazon CloudWatch Logs.
- CloudTrail Event history retains events for 90 days, so configure a trail for longer investigations.

## 🚫 What Does Not Get Approved
- Actions the classifier doesn’t approve return to the user, as do timeouts and other review failures, which never grant automatic approval.
- An approval to send to the original recipients can’t be reused for the wider audience.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22232-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22232-2.jpg)

#AmazonQuick #SmartApprovals #AI #CloudTrail #Automation

---

*Source: [Smart Approvals in Amazon Quick: Human oversight where it matters | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/smart-approvals-in-amazon-quick-human-oversight-where-it-matters/)*
