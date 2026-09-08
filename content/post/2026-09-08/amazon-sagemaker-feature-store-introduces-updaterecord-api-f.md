---
title: "Amazon SageMaker Feature Store introduces UpdateRecord API for feature-level writes"
slug: "amazon-sagemaker-feature-store-introduces-updaterecord-api-for-feature-level-writes"
description: "Amazon SageMaker Feature Store has introduced the UpdateRecord API, allowing users to update specific feature values without reading or rewriting entire records."
date: 2026-09-09T00:31:26+05:30
tags: [AmazonSageMaker, MachineLearning, MLOps, AWS]
categories: ["Machine Learning", "Cloud Computing", "Data Management"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/Amazon-SageMaker-Feature-Store-introduces-UpdateRecord-for-feature-level-writes.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker Feature Store introduces UpdateRecord API for feature-level writes

Amazon SageMaker Feature Store has introduced the UpdateRecord API, allowing users to update specific feature values without reading or rewriting entire records.

## 🔍 Overview
Amazon SageMaker Feature Store is a fully managed repository used to store, share, and manage machine learning (ML) features, which are the processed data used for generating predictions and training models. Features are organized into Feature Groups, which are logical collections of related features used by one or more ML models.

## 💡 Why it matters
Until now, updating a single feature value within a feature group required a full read-modify-write cycle using PutRecord. The UpdateRecord API removes this cycle, as the client application only needs to call the API with the changed features. Features not included in the request are preserved as-is.

## 🧩 How it works
The Feature Store service performs the following steps during an UpdateRecord call:
* Validates AWS Identity and Access Management (IAM) permissions.
* Checks EventTime ordering to reject stale writes.
* Performs an atomic merge of the provided features.

To ensure training datasets remain accurate, a full record snapshot is automatically replicated to the offline store.

## ⚙️ Key details
The UpdateRecord API requires the following parameters:

| Parameter | Description |
| :--- | :--- |
| FeatureGroupName | The target feature group |
| RecordIdentifierValueAsString | The primary key of the record to update |
| Features | A list of one or more feature values to set (up to 100 per call) |
| EventTime | Must be newer than the existing stored EventTime or the call is rejected with an HTTP 409 error |
| TtlDuration (optional) | Override or set a per-record time-to-live (TTL) |

Note: UpdateRecord is not an upsert; the record must already exist.

## 🚀 Availability
This capability is available for both online store tiers:

* **In-Memory Tier (Amazon ElastiCache-backed):** Feature-level writes work on all existing In-Memory feature groups out of the box.
* **Standard Tier (Amazon DynamoDB-backed):** Requires a new storage format named Standard_V2 to support feature-level writes. 

Users of the Standard Tier can transition to Standard_V2 by:
1. Using the Feature Processor SDK to read records from an existing Standard feature group and re-ingesting them into a new Standard_V2 feature group.
2. Calling UpdateFeatureGroup with `OnlineStoreConfig.StorageType = “Standard_V2”` to flip the format in place. Once declared as Standard_V2, calls to PutRecord or BatchWriteRecord will update the underlying format to Standard_V2.

#AmazonSageMaker #MachineLearning #MLOps #AWS

---

*Source: [Amazon SageMaker Feature Store introduces UpdateRecord for feature-level writes | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/amazon-sagemaker-feature-store-introduces-updaterecord-for-feature-level-writes/)*
