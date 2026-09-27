---
title: "Ubicloud Launches Open Source Cloud for Bare Metal Providers"
slug: "ubicloud-launches-open-source-cloud-for-bare-metal-providers"
description: "Ubicloud is an open source cloud that can run anywhere, providing IaaS cloud features on bare metal providers including AWS Bare Metal, Leaseweb, and Hetzner."
date: 2026-09-27T18:01:26+05:30
tags: [Ubicloud, OpenSource, IaaS, CloudComputing, BareMetal]
categories: ["AI", "Cloud Infrastructure", "Open Source Software", "Information Technology"]
image: "https://avatars.githubusercontent.com/u/121406468?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Ubicloud Launches Open Source Cloud for Bare Metal Providers

Ubicloud is an open source cloud that can run anywhere, providing IaaS cloud features on bare metal providers including AWS Bare Metal, Leaseweb, and Hetzner.

## 🔍 Overview
Ubicloud offers an open source alternative to traditional cloud services to reduce costs and return infrastructure control to the user. The project aims to implement 10% of cloud services that account for 80% of consumption.

## 🧩 How it works
Ubicloud utilizes a control plane to manage a data plane that leverages open source software. The control plane is responsible for cloudifying bare metal Linux machines.

| Component | Technical Implementation |
| :--- | :--- |
| Elastic Compute | Control plane communicates with Linux bare metal servers using SSH |
| Virtual Machine Monitor | Cloud Hypervisor, with each instance contained in Linux namespaces |
| Networking | IPsec tunneling for encrypted private networks |
| Firewalls & Load Balancers | Linux nftables |
| Block Storage | Storage Performance Development Toolkit (SPDK) |

## ⚙️ Key details
* **Networking:** Supports dual-stack IPv4 and IPv6 with both public and private networking. Ubicloud assigns IPv6 addresses to VMs, or users can add IPv4 addresses leased from their provider to the control plane. Each customer's VMs operate in their own networking namespace.
* **Storage:** Non-replicated block storage is provided via SPDK, which allows for future implementation of replication and snapshots. Data encryption keys are encrypted following security best practices.
* **Access Control:** Attribute-Based Access Control (ABAC) allows for the definition of roles, attributes, and permissions for fine-grained resource access.

## 🚀 Availability
Users can set up Ubicloud themselves on supported providers or use a managed service. The managed cloud is approximately 3x cheaper than AWS.

#Ubicloud #OpenSource #IaaS #CloudComputing #BareMetal

---

*Source: [ubicloud/ubicloud](https://github.com/ubicloud/ubicloud)*
