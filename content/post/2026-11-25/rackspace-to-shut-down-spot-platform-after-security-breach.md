---
title: "Rackspace to Shut Down Spot Platform After Security Breach"
slug: "rackspace-to-shut-down-spot-platform-after-security-breach"
description: "Rackspace is shutting down its Rackspace Spot cloud platform, which allows organizations to deploy and manage containerized applications using Kubernetes, following a security breach that allowed..."
date: 2026-11-25T12:10:39+05:30
tags: [Rackspace, Security, Kubernetes, Cloud, DataBreach]
categories: ["AI", "Cloud Computing", "Cybersecurity", "Containers", "IT Infrastructure"]
image: "https://www.bleepstatic.com/content/hl-images/2022/12/09/Rackspace.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Rackspace to Shut Down Spot Platform After Security Breach

Rackspace is shutting down its Rackspace Spot cloud platform, which allows organizations to deploy and manage containerized applications using Kubernetes, following a security breach that allowed hackers to access customer clusters and secrets. Customers are given until December 8 to migrate their services and download their data before the platform is permanently discontinued.

## 🚨 The Breach and Discovery

The decision to discontinue the service comes after a security incident that occurred on November 17, when hackers breached Rackspace Spot using compromised credentials. The intrusion allowed unauthorized actors to create pods in customer Kubernetes clusters, read Kubernetes Secrets, and list nodes and volumes. Rackspace discovered the intrusion on November 18 following a customer report and subsequently disabled access to the platform's administration console to secure its infrastructure.

The service was restored on November 21 following an extended outage. Rackspace stated that the affected Spot environment is segmented from its core infrastructure and that it has not identified evidence of unauthorized access to its core systems or the environments of other Rackspace customers.

## ⚙️ Customer Instructions and Indicators of Compromise

Rackspace has instructed all Spot customers to treat their API tokens, refresh tokens, kubeconfigs, and Kubernetes Secrets as potentially compromised, regardless of whether they previously received a breach notification. Customers are also advised to review access logs dating back to November 16 and search for suspicious Kubernetes objects associated with the attack.

The following indicators of compromise have been provided for customers to search within their logs:

| Indicator Type | Details |
| :--- | :--- |
| IP Address | 23.224.79.106 |
| IP Range | 23.224.0.0/15 |
| Suspicious Kubernetes Pod and Object Prefixes | i1, glm-, and probe |

## 📅 Shutdown Details

Rackspace announced the shutdown in a new security notification, stating it had decided to wind down the Rackspace Spot service to provide a clear path forward for customers. The service will be permanently discontinued on December 8, 2026, at 5 PM Central Time, at which point all remaining workloads will be terminated and customer data will no longer be accessible. Customers are instructed to retrieve their data and migrate their workloads to different platforms before this deadline.

## 💡 Customer Response

The shutdown announcement has prompted disappointment among Rackspace Spot customers, with some urging the company to reconsider and offering to pay more to keep the platform operational. In a Reddit discussion, one customer said they believed users would be willing to pay higher prices to keep the service running. Other customers expressed concerns about affordable alternatives and the impact the shutdown would have on their existing infrastructure, while others praised the service for its affordability. Rackspace has not indicated whether it will reconsider the shutdown decision or offer customers additional time to migrate their workloads.

#Rackspace #Security #Kubernetes #Cloud #DataBreach

---

*Source: [Rackspace shuts down Spot cloud platform after security breach](https://www.bleepingcomputer.com/news/security/rackspace-shuts-down-spot-cloud-platform-after-security-breach/)*
