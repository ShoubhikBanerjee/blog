---
title: "Private VPC Connectivity for Amazon Quick Enterprise Data Sources"
slug: "private-vpc-connectivity-for-amazon-quick-enterprise-data-sources"
description: "Amazon Quick now supports private connections to on‑premises data sources, letting enterprises keep regulated data behind firewalls while still using AI‑powered search, analytics, and automation."
date: 2026-10-22T18:03:17+05:30
tags: [AWS, AmazonQuick, VPC, EnterpriseAI, DataSecurity]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Enterprise Data", "Networking"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/19/ML-20213-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Private VPC Connectivity for Amazon Quick Enterprise Data Sources

Amazon Quick now supports private connections to on‑premises data sources, letting enterprises keep regulated data behind firewalls while still using AI‑powered search, analytics, and automation.

## 🔍 Overview
- Amazon Quick is an AI‑powered workspace that brings search, analytics, research, and automation into a single conversational experience.
- When enterprise data sits behind a corporate firewall or in a private on‑premises data center, there is no direct network path from AWS, even though the AI agents and dashboards in Amazon Quick can query virtually any data source.
- Regulatory frameworks such as HIPAA, FedRAMP, and PCI‑DSS often mandate that sensitive data remain within controlled network boundaries.

## 🛠️ How it Works
- Requires an existing AWS Direct Connect or Site‑to‑Site VPN linking the on‑premises environment to the VPC.
- Configure VPC endpoints powered by AWS PrivateLink so Quick reaches private resources over the AWS backbone.
- Layer security groups and VPC endpoint policies for defense in depth.
- Data‑fetching traffic (when Quick reaches into your network) travels through the VPC connection, never over the public internet.

## 📊 Supported Data Sources
| Source Type | Example Databases | Connection Method |
|-------------|-------------------|-------------------|
| On‑premises relational databases | PostgreSQL, MySQL, SQL Server, Oracle, and others | Queried by Amazon Quick Sight through ENIs placed in the VPC (heaviest consumer of VPC connections) |
| Knowledge‑base source (VPC‑only) | Amazon Redshift | Supported VPC connection for Quick Index |
| Other knowledge sources (no VPC) | Confluence, SharePoint, Box, Google Drive, OneDrive, Amazon S3 | Cannot use a Quick VPC connection today (but S3 bucket access can be restricted via a VPC endpoint bucket policy) |

## ⚙️ Automation Features with Private Connectivity
- **Quick Agents** underpin all conversational interactions and can invoke action connectors directly; traffic to privately hosted MCP servers or internal APIs flows through the VPC connection.
- **Quick Flows** handle repeatable tasks; they invoke action connectors, including MCP servers in the VPC.
- **Quick Automate** handles complex, multi‑system orchestration with human‑in‑the‑loop; any workflow calling an internal API routes through the VPC path.
- **Quick Apps** inherit the same VPC connectivity as Quick Sight and Flows for interactive web applications.
- **Quick Spaces** organize content but do not initiate their own data connections.

## 🚀 Availability & Requirements
- An active AWS account with an Amazon Quick Enterprise subscription (VPC connections require Enterprise edition).
- An existing VPC in the AWS Region where Quick is deployed.
- Direct Connect or Site‑to‑Site VPN already established.
- Quick website VPC endpoints are not available in the AWS China Regions or the AWS GovCloud (US) Regions.

## 💡 Why It Matters
- Enables enterprises to keep regulated data within controlled network boundaries while still leveraging AI‑driven search, analytics, and automation.
- Provides a private, AWS‑backbone path that avoids the public internet, meeting compliance mandates such as HIPAA, FedRAMP, and PCI‑DSS.
- Offers defense‑in‑depth security through VPC endpoint policies and security groups.

#AWS #AmazonQuick #VPC #EnterpriseAI #DataSecurity

---

*Source: [Securing Quick access from corporate networks with AWS PrivateLink | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/securing-quick-access-from-corporate-networks-with-aws-privatelink/)*
