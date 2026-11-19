---
title: "Amazon Bedrock AgentCore Gateway Networking Requirements for Private MCP and REST APIs"
slug: "amazon-bedrock-agentcore-gateway-networking-requirements-for-private-mcp-and-rest-apis"
description: "Amazon Bedrock AgentCore Gateway now supports agents that call internal REST APIs and Model Context Protocol (MCP) servers, provided they meet specific network ownership and traffic inspection..."
date: 2026-11-19T22:12:49+05:30
tags: [AmazonBedrock, AgentCore, AI, Networking, MCP]
categories: ["AI", "AI Agents", "Cloud Networking", "Amazon Web Services", "Model Context Protocol"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22132-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock AgentCore Gateway Networking Requirements for Private MCP and REST APIs

Amazon Bedrock AgentCore Gateway now supports agents that call internal REST APIs and Model Context Protocol (MCP) servers, provided they meet specific network ownership and traffic inspection requirements.

## 🔍 Overview
Amazon Bedrock AgentCore is a platform to build, connect, and optimize agents at scale, with any framework or model. The Gateway connects to private targets through an Amazon VPC Lattice resource gateway. This update clarifies where to place the resource gateway, who owns each network component, and the configuration decisions required for traffic to cross a central firewall in both directions.

## 🧩 How it works
The AgentCore Gateway reaches private targets through two private endpoint modes:
- **Managed mode**: AgentCore creates the resource gateway for you. This fits environments where the Gateway account can own the subnets it runs in.
- **Self-managed mode**: You create the resource gateway and give the target a resource configuration. As documented, this places it in subnets with direct access to the backend, fitting environments that do not require inspection between the Gateway and the tool.

In the pattern built and tested in the US East (N. Virginia) AWS Region (us-east-1), the network account owns the resource gateway and places it in subnets routed through AWS Transit Gateway. This ensures every request and reply between VPCs crosses the central firewall in an inspection VPC. The network team keeps ownership of every subnet, and traffic between the Gateway and private APIs and MCP servers crosses the central firewall in both directions.

## ⚙️ Key details
The architecture relies on specific VPC Lattice objects and sharing mechanisms:
- **Resource gateway**: The Amazon VPC Lattice entry point into a VPC, utilizing elastic network interfaces (ENIs) in subnets you choose.
- **Resource configuration**: A VPC Lattice object that names one backend (an internal load balancer or VPC endpoint DNS name and port) behind a resource gateway. This can be shared with other accounts through AWS Resource Access Manager (AWS RAM).

Key ownership and traffic rules include:
- A network account owns every VPC, subnet, and AWS Transit Gateway attachment, sharing application subnets through AWS RAM.
- The Gateway account can own subnets that reach your tools.
- The Gateway and application accounts build only in subnets shared to them through AWS RAM.
- Tools are reachable on public endpoints if central inspection is not required for that specific flow, but in the documented pattern, every flow between VPCs crosses the central firewall.
- The central firewall in the inspection VPC inspects the traffic between the Gateway and your private APIs and MCP servers.

## 🚀 Availability
The pattern was validated in a lab with three member accounts and a management account in AWS Organizations. The AWS CloudFormation templates, test scripts, test evidence, and reference material (address plan, full validation checks, troubleshooting, quotas) are available in the companion repository.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/22132-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22132-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22132-3.jpg)

#AmazonBedrock #AgentCore #AI #Networking #MCP

---

*Source: [Connect Amazon Bedrock AgentCore Gateway to private APIs in a hub-and-spoke network with centralized inspection | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/connect-amazon-bedrock-agentcore-gateway-to-private-apis-in-a-hub-and-spoke-network-with-centralized-inspection/)*
