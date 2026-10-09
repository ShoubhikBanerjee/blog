---
title: "Veeam Releases Recovery Orchestrator v13.1 with Hyper-V and Azure Support"
slug: "veeam-releases-recovery-orchestrator-v13-1-with-hyper-v-and-azure-support"
description: "Veeam has launched Veeam Recovery Orchestrator v13.1 as part of the Veeam Data Platform Premium Edition. This release introduces quality-of-life improvements designed to make data orchestration..."
date: 2026-10-09T12:11:21+05:30
tags: [Veeam, DisasterRecovery, HyperV, CloudBackup, DataProtection]
categories: ["AI", "Disaster Recovery", "Cloud Infrastructure", "Data Management"]
image: "https://img.veeam.com/blog/wp-content/uploads/2026/09/18162545/Emilee-Tellez.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Veeam Releases Recovery Orchestrator v13.1 with Hyper-V and Azure Support

Veeam has launched Veeam Recovery Orchestrator v13.1 as part of the Veeam Data Platform Premium Edition. This release introduces quality-of-life improvements designed to make data orchestration simpler and more flexible, featuring new stand-alone host support, direct-to-cloud restoration, and read-only repository access.

## 🖥️ Stand-Alone Hyper-V and Cross-Platform Recovery

Orchestrator v13.1 introduces support for a stand-alone Hyper-V host as a recovery target, accommodating both local and shared storage. This update also introduces new migration and recovery pathways:

* **Cross-Platform Restores:** vSphere environments can perform cross-platform restores from vSphere VM backups to a stand-alone Hyper-V host. This enables organizations to utilize a lower-cost Hyper-V disaster recovery site to pilot potential platform migrations on a single host.
* **Direct Azure Restores:** Hyper-V VM backups can now be restored directly to Azure, joining existing support for vSphere VM and Veeam Agent backups. This feature also supports script injection to the restored virtual machines.

## 🛡️ Read-Only Repositories and Cleanroom Protection

Building on Veeam Backup & Replication v13.1 features, object storage repositories can now connect to Orchestrator’s embedded Veeam backup server in read-only mode. This configuration provides several key advantages:

* **Continuous Access:** Users maintain constant access to the latest restore points, including imported backups, to test recovery plans.
* **Cleanroom Security:** Read-only access allows cleanroom recovery environments to pull current data without creating a pathway back to production.
* **Automatic Handoffs:** If the production Veeam Backup & Replication server goes down, the embedded backup server can take over failover. This update keeps the data behind that handoff current automatically, eliminating the need for manual connection refreshes.

## 📍 Upgraded Recovery Locations

Recovery locations have received two key upgrades designed to improve precision without sacrificing automation:

* **Specific Targeting:** While automatic selection remains available, users can now target recovery directly to a specific Veeam backup server and the specific repositories it manages.
* **Map From Any Source Network:** This catch-all network mapping configuration option allows recovery locations to recover VMs from source networks that have not been explicitly mapped, preventing recovery processes from failing when an unexpected network is encountered.

## ⚙️ Simplified Day 2 Operations

Day 2 operations and maintenance tasks have been streamlined through a unified installer, a new Scheduled Tasks page, and the new Veeam Updater plug-in, which can be launched directly from the About page in the Orchestrator web UI.

| Feature | Capability |
| :--- | :--- |
| **Update Scheduling & Automation** | Allows users to define maintenance windows and control when updates are installed. |
| **Mandatory Updates** | Enforces required patch levels across all managed Veeam Backup & Replication components. |
| **Bulk Update Management** | Allows users to update multiple infrastructure components simultaneously to streamline maintenance. |

![figure](https://img.veeam.com/blog/wp-content/uploads/2026/10/25140142/image-20260924-124816.png)

![figure](https://img.veeam.com/blog/wp-content/uploads/2026/10/25140158/image-20260924-124851.png)

#Veeam #DisasterRecovery #HyperV #CloudBackup #DataProtection

---

*Source: [What's New in Veeam Recovery Orchestrator v13.1](https://www.veeam.com/blog/whats-new-in-veeam-recovery-orchestrator-13-1.html)*
