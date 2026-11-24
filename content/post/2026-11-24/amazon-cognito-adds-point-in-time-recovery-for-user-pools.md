---
title: "Amazon Cognito Adds Point-in-Time Recovery for User Pools"
slug: "amazon-cognito-adds-point-in-time-recovery-for-user-pools"
description: "Amazon Cognito has introduced point-in-time recovery (PITR) for user pools, enabling administrators to restore user data to an earlier point in time. This feature addresses challenges that previously..."
date: 2026-11-24T12:08:32+05:30
tags: []
categories: ["AI"]
image: "https://d2908q01vomqb2.cloudfront.net/827bfc458708f0b442009c9c9836f7e4b65557fb/2020/06/03/Blog-Post_thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Cognito Adds Point-in-Time Recovery for User Pools

Amazon Cognito has introduced point-in-time recovery (PITR) for user pools, enabling administrators to restore user data to an earlier point in time. This feature addresses challenges that previously required building custom backup solutions, which were time-consuming to build and operate, versioning exports to find a clean recovery point, and reconstructing pools from backups. The new capability automatically tracks changes on eligible user pools, allowing recovery to any point within the defined recovery window.

## 🔍 Overview

Before this launch, protecting user pool data required manual approaches like exporting user attributes and group data on a schedule. These methods had significant limitations: versioning exports was complex, and reconstructing a pool from them was error-prone. Additionally, users who were restored received new sub identifiers, potentially breaking downstream references to the originals.

## 🧩 How it works

Amazon Cognito now tracks changes to eligible user pools, enabling recovery to any point within the recovery window. The recovery window duration depends on the user pool's feature plan:

| Feature Plan | Recovery Window |
|--------------|----------------|
| Essentials   | Up to 1 day     |
| Plus         | Up to 14 days   |

The window accrues from the time the pool is on an eligible feature plan, and recovery can only target a point at which PITR coverage already existed.

The recovery process begins when you initiate a restore to a target time that is at least 15 minutes in the past and no earlier than the pool's creation time. Before changes are applied, Amazon Cognito pauses write operations to the user pool and generates a preview for your review. Read operations and sign-in continue to work normally during this process. The system reports how many users, groups, MFA settings, and passkeys the recovery would create, update, or delete.

If the preview looks correct, you approve the recovery with StartPointInTimeRecovery. Amazon Cognito then restores the pool to its state at the target time. If the preview is incorrect, you can cancel with CancelPointInTimeRecovery, applying no changes and resuming write operations.

## ⚙️ Key details

- Recovery restores passwords for users it recreates. A user who still exists and changed their password after the target time keeps the same password.
- The recovery does not revert password changes, so users who legitimately changed their credentials retain them.
- Users who are restored receive new sub identifiers, which may break downstream references.
- Passwords, multi-factor authentication (MFA) settings, and passkeys might not be recovered, requiring affected users to reset their credentials.

You can run one recovery at a time per user pool, and one successful recovery per 24 hours per pool. Recovery is initiated from the pool's primary Region and cannot start while a multi-Region replication (MRR) operation is in progress on the pool.

## 💡 Example scenario

Consider AnyCompany, which runs its user sign-in on an Amazon Cognito user pool named anycompany-prod-user-pool. At 15:45 PDT, an operator runs a bulk change intended to set an attribute on a subset of users. A defect in the script instead deletes and modifies users. By 15:54 PDT, support receives cases of failed sign-ins, and the operator halts the script. Point-in-time recovery allows administrators to restore the pool to a state before the erroneous bulk operation occurred.

## 🚀 Availability

Point-in-time recovery is now enabled automatically for user pools on eligible feature plans (Essentials or Plus). To initiate recovery, you need an AWS account with an Amazon Cognito user pool on one of these plans.

---

*Source: [Protect identity data with point-in-time recovery in Amazon Cognito | Amazon Web Services](https://aws.amazon.com/blogs/security/protect-identity-data-with-point-in-time-recovery-in-amazon-cognito/)*
