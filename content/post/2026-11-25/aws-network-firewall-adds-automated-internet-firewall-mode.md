---
title: "AWS Network Firewall adds automated internet firewall mode"
slug: "aws-network-firewall-adds-automated-internet-firewall-mode"
description: "AWS Network Firewall has launched a new automated internet firewall mode, currently in Preview. This mode applies centrally defined firewall rules to traffic at the internet gateway of each virtual..."
date: 2026-11-25T06:12:19+05:30
tags: [AWS, NetworkFirewall, VPC, CloudSecurity, Networking]
categories: ["AI", "Cloud Networking", "Security", "Infrastructure", "AWS"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/aif-main-image-1200x600-1.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Network Firewall adds automated internet firewall mode

AWS Network Firewall has launched a new automated internet firewall mode, currently in Preview. This mode applies centrally defined firewall rules to traffic at the internet gateway of each virtual private cloud (VPC), simplifying the architecture required to inspect internet-bound and inbound traffic.

## 🔍 Overview
The new mode removes the need to deploy firewall endpoints and NAT gateways in each VPC. Previously, inspecting a VPC's internet traffic meant routing each subnet through a firewall endpoint, while resources needing outbound-only connectivity routed through a NAT gateway. In the new mode, a subnet that reaches the internet requires only one route, directly to the internet gateway, where the firewall inspects the traffic and performs built-in network address translation (NAT) for outbound-only connections.

## 🧩 How it works

- **Per-VPC inspection**: Each VPC gets its own firewall for inbound and outbound IPv4 and IPv6 traffic.
- **Built-in NAT**: For outbound-only connectivity, the firewall first inspects the traffic and then performs NAT, allowing rules and logs to see each workload's private IP address. NAT translates outbound IPv4 connections from resources without a public IP address; IPv6 traffic is not translated.
- **Centralized management**: Policies are defined in AWS Network Security Manager or started from an AWS managed template. You can create a scope that includes all existing and future VPCs, ensuring the policy applies automatically when teams create new VPCs.
- **Overlapping CIDR support**: Because traffic is inspected at each VPC's internet gateway rather than in a shared inspection network, the same central policy works for VPCs with overlapping Classless Inter-Domain Routing (CIDR) ranges.
- **NAT address selection**: If destinations accept only allowlisted source addresses, an Amazon VPC IP Address Manager (IPAM) policy allows you to choose the NAT addresses used by the automated internet firewall mode.

## ⚙️ Key details

| Feature | Detail |
| :--- | :--- |
| **Throughput** | Each VPC's firewall supports up to 100 Gbps in each Availability Zone |
| **Rule Groups** | AWS security experts maintain and update AWS managed rule groups to protect against changing threats |
| **Default Template** | You can start from the `AWSManagedTemplateIGWFirewallBaseline` AWS managed template |
| **Policy Engine** | Uses Network Firewall Next Generation firewall policies |

## 💡 Why it matters
This mode simplifies the traditional VPC networking model by moving inspection to the internet gateway. Instead of sharing firewall capacity across Availability Zones when using VPC endpoint associations, each VPC's firewall in this mode brings its own inspection capacity. New users of internet traffic inspection can start with AWS managed rule groups, which are deployed centrally across the environment to help protect workloads.

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/aif-fig1-r25-r30.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/aif-fig2-r14-r30.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/aif-fig3-combined-r27d-r30.png)

#AWS #NetworkFirewall #VPC #CloudSecurity #Networking

---

*Source: [AWS Network Firewall introduces automated internet firewall mode (Preview) | Amazon Web Services](https://aws.amazon.com/blogs/security/aws-network-firewall-introduces-automated-internet-firewall-mode-preview/)*
