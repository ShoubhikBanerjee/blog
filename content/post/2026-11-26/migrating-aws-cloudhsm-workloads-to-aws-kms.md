---
title: "Migrating AWS CloudHSM Workloads to AWS KMS"
slug: "migrating-aws-cloudhsm-workloads-to-aws-kms"
description: "AWS Key Management Service (AWS KMS) now supports the security certifications, algorithms, and performance required by most AWS CloudHSM workloads, enabling organizations to migrate and significantly..."
date: 2026-11-26T12:19:42+05:30
tags: [AWSKMS, AWSCloudHSM, SecurityMigration, Cryptography, PostQuantum]
categories: ["AI", "Cloud Security", "Cryptographic Infrastructure", "Migration", "AWS Services"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/storage.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# Migrating AWS CloudHSM Workloads to AWS KMS

AWS Key Management Service (AWS KMS) now supports the security certifications, algorithms, and performance required by most AWS CloudHSM workloads, enabling organizations to migrate and significantly reduce costs while eliminating hardware security module (HSM) provisioning, patching, and high-availability management.

## 🔍 Overview

Most AWS CloudHSM workloads can migrate to AWS KMS. Organizations are advised to review their compliance documentation for explicit single-tenant language, as many organizations find that it is assumed rather than mandated. While AWS KMS embeds cryptographic best practices in a managed service, some payment systems still rely on older cryptography such as TDES. For these cases, AWS Payment Cryptography supports payment use cases, including TDES-based algorithms such as CVV2, ARQC, and PIN validation, and provides low-level algorithms like AES-CBC that third-party systems might require for interoperability.

## 🧩 How it works

Migration consists of three parts: updating application code to call KMS APIs, rotating or importing cryptographic keys, and transitioning existing data.

*   **Application Refactoring:** This is the bulk of the effort. The interfaces involved are a communication pattern, not an architectural constraint. Organizations are encouraged to contact their AWS account team to assess the effort needed to use modern RESTful interfaces and to evaluate whether dependencies on older systems can be retired as part of security modernization.
*   **Key Management:** If AWS CloudHSM allows you to export (wrap) a copy of your private key, you can import it directly into AWS KMS to maintain continuity. If the key is non-exportable, you must create a new key pair in AWS KMS. During the transition, the AWS CloudHSM private key continues to sign existing workloads, while a new asymmetric KMS key (or the imported key) signs new data flowing to AWS KMS.
*   **Data Transition:** You re-encrypt previously encrypted data under KMS keys. Existing signatures remain verifiable without AWS CloudHSM. You can complete each part of the migration gradually with zero downtime. For organizations that created a new key pair, export the CloudHSM public key before decommissioning and use it to verify existing signatures locally with libraries such as AWS-LC or OpenSSL.

## ⚙️ Key details

The following points outline specific considerations and capabilities for the migration:

*   AWS KMS does not support importing public keys.
*   Traffic can be shifted from AWS CloudHSM to AWS KMS at your own pace.
*   Per-operation pricing is only one of several factors affecting cost; organizations should also consider saved staff time, patching, and high-availability management.
*   With envelope encryption, optional data key caching can further reduce API call volume.
*   Because application code is being refactored, this migration provides an opportunity to adopt post-quantum cryptography (PQC) algorithms when creating new signing keys.
*   AI-assisted code transformation tools can reduce the workload associated with application refactoring.

## 💡 Why it matters

Migrating from AWS CloudHSM to AWS KMS allows organizations to eliminate the operational overhead of managing HSMs while retaining the security features required for their workloads. The process supports a gradual transition with zero downtime and opens the door to modernizing cryptographic dependencies, including the adoption of post-quantum algorithms.

![Figure 1: Digital signature migration](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/Figure-1-Digital-signature-migration.png)

![Figure 2: Encryption migration with AWS KMS API](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/Figure-2-Encryption-migration-with-AWS-KMS-API.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/Figure-1-Digital-signature-migration.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/24/Figure-2-Encryption-migration-with-AWS-KMS-API.png)

#AWSKMS #AWSCloudHSM #SecurityMigration #Cryptography #PostQuantum

---

*Source: [Reduce operational overhead by migrating from AWS CloudHSM to AWS KMS | Amazon Web Services](https://aws.amazon.com/blogs/security/reduce-operational-overhead-by-migrating-from-aws-cloudhsm-to-aws-kms/)*
