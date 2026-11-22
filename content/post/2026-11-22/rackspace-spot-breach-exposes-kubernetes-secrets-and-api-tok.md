---
title: "Rackspace Spot Breach Exposes Kubernetes Secrets and API Tokens"
slug: "rackspace-spot-breach-exposes-kubernetes-secrets-and-api-tokens"
description: "Rackspace has warned customers that hackers breached its Rackspace Spot cloud platform using compromised credentials. The intrusion allowed unauthorized parties to deploy workloads and access..."
date: 2026-11-22T18:07:49+05:30
tags: [Rackspace, Kubernetes, CloudSecurity, DataBreach]
categories: ["AI", "Cloud Computing", "Cybersecurity", "Kubernetes"]
image: "https://www.bleepstatic.com/content/hl-images/2022/12/09/Rackspace.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Rackspace Spot Breach Exposes Kubernetes Secrets and API Tokens

Rackspace has warned customers that hackers breached its Rackspace Spot cloud platform using compromised credentials. The intrusion allowed unauthorized parties to deploy workloads and access sensitive Kubernetes secrets within customer clusters.

## 🔍 Overview

Rackspace disclosed the breach in a notification to affected customers, stating that attackers accessed parts of the platform on November 17, 2026, between approximately 00:20 and 22:00 UTC. The company learned of the intrusion on November 18 after receiving a customer report and confirmed that the recipient's organization was affected that same day.

## ⚙️ Key details

- **Access Method:** An unauthorized party used leaked credentials to act as legitimate users in some customer organizations.
- **Actions Taken:** Attackers created pods in Kubernetes clusters, read Kubernetes Secrets, and listed nodes and volumes.
- **Exposure Risk:** Attackers could have read any Secret stored in an affected user's clusters, as well as any Spot API tokens or refresh tokens held by that user.
- **Indicators:** The breach was associated with IP address 23.224.79.106, IP range 23.224.0.0/15, and suspicious Kubernetes pod and object prefixes including `i1`, `glm-`, and `probe`.

## 🛡️ Remediation and Response

Rackspace stated that it has revoked affected tokens and sessions, removed the unauthorized pods, rotated keys, and strengthened access controls and monitoring. Affected customers were instructed to:

*   Reissue their Spot API tokens.
*   Replace refresh tokens used in automation tools.
*   Download fresh Kubernetes configuration files.
*   Rotate credentials stored in their cluster Secrets.
*   Analyze logs associated with databases, container registries, Git repositories, cloud storage, and third-party services dating back to November 17 to identify possible abuse of exposed credentials.

The breach caused an extended outage of the Rackspace Spot administration console, temporarily preventing customers from managing their clusters or rotating credentials. Sirish Raghuram, co-founder and Chief Growth Officer of Platform9, explained that the team deliberately disabled access while securing its infrastructure. Rackspace announced that service was fully restored on November 21.

#Rackspace #Kubernetes #CloudSecurity #DataBreach

---

*Source: [Rackspace Spot breach let hackers access customer Kubernetes secrets](https://www.bleepingcomputer.com/news/security/rackspace-spot-breach-let-hackers-access-customer-kubernetes-secrets/)*
