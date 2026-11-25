---
title: "AWS Network Firewall Adds Context-Aware Rules and Next Generation Policies"
slug: "aws-network-firewall-adds-context-aware-rules-and-next-generation-policies"
description: "AWS Network Firewall has updated its capabilities to support context-aware rules, allowing you to match traffic based on the AWS resources that send and receive it rather than by their IP addresses...."
date: 2026-11-25T22:10:10+05:30
tags: [AWS, NetworkFirewall, CloudSecurity, VPC, TransitGateway]
categories: ["AI", "Cloud Computing", "Cybersecurity", "Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/4026.main_.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Network Firewall Adds Context-Aware Rules and Next Generation Policies

AWS Network Firewall has updated its capabilities to support context-aware rules, allowing you to match traffic based on the AWS resources that send and receive it rather than by their IP addresses. Alongside this, AWS has introduced Next Generation policies, which separate access control and threat protection into independent engines to help simplify firewall management and policy scaling.

## 🔍 Overview
Rules that match on IP addresses must keep up with every workload that scales out, is replaced, or moves. Short-lived workloads are the hardest to keep up with; for example, a VPC-attached AWS Lambda function can scale out and start sending traffic before an updated IP list reaches the firewall. Context-aware rules solve this issue by allowing you to filter a function's traffic by the security group attached to it, or by naming a virtual private cloud (VPC), a subnet, or a transit gateway attachment.

## 🧩 How it works
Context-aware rules require transit gateway-attached firewalls and function by combining a control path and a data path:

* **The Control Path**: A context store—which is a catalog of the AWS resources that can send and receive traffic through a transit gateway—tells the firewall which resources exist. You create this in AWS Network Manager and associate it with the transit gateway that your firewall uses.
* **The Data Path**: The transit gateway adds the context of the sender (including its VPC, subnet, transit gateway attachment, and security groups) to each packet.
* **The Firewall Engine**: The firewall receives these two paths, reads the context on each packet, and matches it against your configured rules. Source context works with every protocol, while destination context requires TCP-based rules because the firewall learns the receiving resource from return traffic.

Here is how context rules apply to specific AWS resources:

| Resource Type | Rule Application |
| :--- | :--- |
| **Subnet or VPC** | Applies to each new resource that you launch in it. |
| **Security Group** | Applies to each new resource whose network interface has that security group attached. |
| **Transit Gateway Attachment** | Applies to traffic that enters through that attachment. |

## ⚙️ Next Generation Policies
In a Classic policy, your access rules and threat rules run together in a single stateful engine and share one rule capacity. With Next Generation policies, access control and threat protection each get their own stateful engine in the same firewall, executed in sequence:

1. **Firewall Engine**: This engine handles access control and is drop by default. Built on Suricata 8 firewall mode, it follows each connection through its entire flow (including the TCP handshake and TLS client hello) and evaluates rules along the way up to the application layer.
2. **IPS Engine**: This engine manages threat protection and is pass by default. Traffic allowed by the firewall engine moves here, where the IPS engine checks it using AWS managed rule groups or custom rules that you write.

Because each engine has its own rule capacity, adding access rules does not take capacity away from threat protection. This design allows networking and security teams to work independently on their own configurations without risk of overwriting each other's rules.

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/4026-figure-1-full.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/4026-figure-2-full.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/4026-figure-3-full.png)

#AWS #NetworkFirewall #CloudSecurity #VPC #TransitGateway

---

*Source: [Introducing context-aware rules for AWS Network Firewall | Amazon Web Services](https://aws.amazon.com/blogs/security/introducing-context-aware-rules-for-aws-network-firewall/)*
*Source: [Introducing AWS Network Firewall Next Generation policy | Amazon Web Services](https://aws.amazon.com/blogs/security/introducing-aws-network-firewall-next-generation-policy/)*
