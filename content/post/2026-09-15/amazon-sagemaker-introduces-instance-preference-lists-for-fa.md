---
title: "Amazon SageMaker Introduces Instance Preference Lists for Faster GPU Capacity Access"
slug: "amazon-sagemaker-introduces-instance-preference-lists-for-faster-gpu-capacity-access"
description: "Amazon SageMaker AI announced instance preference lists for training and processing jobs, allowing users to provide an ordered list of up to five instance types so the service can automatically..."
date: 2026-09-15T22:08:30+05:30
tags: [SageMaker, InstancePreferences, GPUCapacity, MachineLearning]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21790-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker Introduces Instance Preference Lists for Faster GPU Capacity Access

Amazon SageMaker AI announced instance preference lists for training and processing jobs, allowing users to provide an ordered list of up to five instance types so the service can automatically launch on the first type with available capacity.

## 🔍 Overview
- Access to the right GPUs is a major challenge for large‑scale AI training and customization.
- During peak demand a preferred GPU may be unavailable, forcing teams to wait or manually try alternatives.
- The new feature lets users specify up to five acceptable instance types, and SageMaker selects the first one with capacity.

## 🧩 How it works
1. **Submit** a training or processing job with an ordered preference list (max 5 types).  
2. SageMaker **validates** the job configuration and the list against supported types and resource limits.  
3. The scheduler performs a **single in‑memory sweep** of the ordered list and picks the first instance type that has capacity.  
4. The chosen instance type is provisioned **immediately**, and the job starts execution.  
5. If none of the listed types have capacity, the job enters an **event‑driven queue** and automatically retries when capacity becomes available. The retry window is limited by **MaxPendingTimeInSeconds**.

## ⚙️ Key details
- Preference list size: up to **five** instance types.  
- Automatic evaluation follows the **priority order** supplied by the user.  
- Removes the need for manual retry loops, monitoring scripts, or custom resubmission logic.  
- **MaxPendingTimeInSeconds** applies only to jobs requesting accelerated computing instances (ml.p, ml.g, ml.trn families) and bounds the total time spent working through the list.  
- The timeout is **not** applied per instance type, and it has no effect on CPU‑only jobs.  
- Works with **Flexible Training Plans**, allowing reserved GPU capacity to be considered before falling back to on‑demand alternatives.

## 🚀 Availability
- The feature is announced and available for use with Amazon SageMaker training and processing jobs.

## 💡 Why it matters
- Faster job starts and higher capacity utilization.  
- Reduces operational overhead from custom retry scripts and monitoring.  
- Enables time‑critical workloads (nightly retraining, production fine‑tuning, scheduled processing) to start promptly, preserving model freshness.  
- Provides a unified way to leverage both reserved capacity (FTP) and on‑demand capacity without manual intervention.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21790-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21790-3.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21790-4.jpg)

#SageMaker #InstancePreferences #GPUCapacity #MachineLearning

---

*Source: [Announcing instance preference lists for Amazon SageMaker AI training jobs | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/announcing-instance-preference-lists-for-amazon-sagemaker-ai-training-jobs/)*
