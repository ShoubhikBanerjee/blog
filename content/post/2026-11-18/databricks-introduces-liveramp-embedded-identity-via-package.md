---
title: "Databricks Introduces LiveRamp Embedded Identity via Packaged Clean Rooms"
slug: "databricks-introduces-liveramp-embedded-identity-via-packaged-clean-rooms"
description: "Traditionally, Databricks customers resolving customer records to a person-based ID like RampID had to manually export PII, wait for a match file, and reload it—adding pipeline complexity, data..."
date: 2026-11-18T18:09:03+05:30
tags: [databricks, identityresolution, cleanrooms, aidataprivacy, unitycatalog]
categories: ["AI", "Data Governance", "AI and Machine Learning", "Privacy and Security", "Cloud Computing"]
image: "https://www.databricks.com/sites/default/files/2026-11/Databricks-LiveRamp.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks Introduces LiveRamp Embedded Identity via Packaged Clean Rooms

# 🔍 Overview

Traditionally, Databricks customers resolving customer records to a person-based ID like RampID had to manually export PII, wait for a match file, and reload it—adding pipeline complexity, data copies, and delays. LiveRamp Embedded Identity on Databricks now eliminates this workflow by integrating identity resolution directly into the data environment.

## 🧩 How it works

### Traditional Workflow (Before)
- Data teams exported PII to an external service.
- Waited for a match file from the service.
- Reloaded the resolved data back into their environment.
- Each step required maintaining pipelines, managing copies of sensitive data, and introducing delays.

### New Workflow (LiveRamp Embedded Identity)
- **LiveRamp Embedded Identity** brings identity resolution to the customer’s Databricks environment.
- Customers retain full control over their data, with no need to export PII externally.
- Minimal setup allows customers to receive resolved RampIDs directly in their Unity Catalog.
- These RampIDs serve as match keys for downstream use cases, such as customer 360, audience building, and activation.

### Packaged Clean Rooms
- A **Databricks clean room** is a secure, isolated environment where multiple parties collaborate without sharing raw data or intellectual property (IP).
- In a standard clean room:
  - Collaborators are peers.
  - Each party approves the other’s code before execution.
  - Data remains private, but collaborators see table aliases and schema details.

- A **packaged clean room** extends privacy to the entire analysis by separating the identity provider (LiveRamp) from the customer.
  - No approval steps are required.
  - Neither party sees the other’s data, tables, or schemas.
  - The provider ships a pre-built analysis as a product, and the customer runs it against their data.
  - This setup enables scalable deployments across multiple customers with minimal setup.

### Identity Resolution via Packaged Clean Rooms
- **Central Clean Room**: A Databricks-managed environment where LiveRamp’s identity logic and customer data interact.
- **OpenSharing Protocol**: Both parties add Unity Catalog assets (tables, models, libraries) to the clean room, granting read-only access without replication.
- **Live Data Access**: OpenSharing ensures the clean room reads the current version of the customer’s input table, not an older extract.
- **Governance & Audit**: Unity Catalog governance is maintained on both sides, and activity is audited in system tables.

### Execution Flow
- A single run writes to two schemas:
  - One schema delivers resolved RampIDs to the customer’s environment.
  - The other schema delivers the identity resolution logic to LiveRamp.
  - Both outputs are shared via OpenSharing and can be queried immediately.
  - For long-term use beyond 30 days, results must be copied to the customer’s cloud storage.
- Both parties track run status, timing, and notebook execution history.
- Shared troubleshooting occurs via run status and output schema, without exposing data.

## ⚙️ Key details

### Components
| Component               | Role                                                                                     | Access Control                                                                                     |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| Central Clean Room       | Hosts the identity resolution logic and data interaction.                                   | Databricks-managed; no administrative access from either party.                                   |
| OpenSharing Protocol    | Enables live, read-only access to customer and LiveRamp assets without replication.           | Unity Catalog governance enforced on both sides.                                                 |
| Unity Catalog           | Governs data assets shared between parties.                                             | Customer controls which tables to add; provider controls exposed assets.                         |

### Benefits
- **No Data Export**: Customer data and resolved results remain private within Unity Catalog.
- **No PII Copies**: Eliminates the need for managing sensitive data copies.
- **No Delays**: Immediate access to resolved RampIDs for analytics and AI workloads.
- **Scalability**: Single packaged clean room can serve multiple customers with identical setups.
- **Privacy**: Both parties retain full control over their data and code, with no shared visibility.
- **Auditability**: Comprehensive logs track run status, timing, and notebook execution.

## 🚀 Availability

LiveRamp Embedded Identity via Packaged Clean Rooms is available on Databricks, enabling customers to perform identity resolution with minimal setup. For detailed setup steps, refer to:
- [LiveRamp’s guide: *Perform RampID identity resolution in Databricks*](https://www.databricks.com/sites/default/files/inline-images/Packaged-Clean-Room-Architecture-v2-selection-1.png?v=1794876472)
- [Databricks Packaged Clean Rooms documentation](https://www.databricks.com/sites/default/files/2023-08/databricks-default.png?v=1712162038)

## 💡 Why it matters

This innovation transforms identity resolution from a manual, pipeline-heavy process into a streamlined, governed workflow. By leveraging packaged clean rooms, customers can:
- **Accelerate analytics**: Access resolved RampIDs directly in their Unity Catalog.
- **Enhance collaboration**: Securely share insights with partners without exposing raw data.
- **Simplify governance**: Maintain Unity Catalog controls while eliminating external data transfers.
- **Reduce operational overhead**: Avoid managing match files, PII copies, and approval workflows.

The result is a more efficient, private, and scalable approach to identity resolution for AI and analytics workloads.


#databricks #identity-resolution #clean-rooms #ai-data-privacy #unity-catalog

---

*Source: [How packaged clean rooms bring RampID to your lakehouse](https://www.databricks.com/blog/liveramp-rampid-identity-resolution-packaged-clean-rooms)*
