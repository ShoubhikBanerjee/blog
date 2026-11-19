---
title: "Amazon SageMaker HyperPod Introduces Workload Recovery and Infrastructure Checks"
slug: "amazon-sagemaker-hyperpod-introduces-workload-recovery-and-infrastructure-checks"
description: "Today, Amazon SageMaker HyperPod introduces workload recovery and infrastructure checks. These features catch failures sooner and raise the goodput of training workloads."
date: 2026-11-19T06:12:23+05:30
tags: [SageMakerHyperPod, MachineLearning, GPUComputing, Kubernetes, AWSInfrastructure]
categories: ["AI", "Machine Learning", "Cloud Infrastructure", "GPU Computing", "Kubernetes"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22383-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker HyperPod Introduces Workload Recovery and Infrastructure Checks

Today, Amazon SageMaker HyperPod introduces workload recovery and infrastructure checks. These features catch failures sooner and raise the goodput of training workloads.

## 🧩 The Challenge
Large training jobs can fail even when every node looks healthy. A GPU with a subtle fault can pass its stress tests and still return wrong values. When a job stalls on an NCCL timeout, it keeps its GPUs, and Slurm still shows it as running. If a device plugin crashes on one node, the job fails with an error that never mentions the plugin.

Teams usually find these problems only after the loss diverges or the job fails, and by then, the compute is spent. Each of these failures lowers goodput, the share of your cluster's time that goes to useful training.

### Types of Failures
*   **Numerical faults:** A GPU can pass every hardware test and still compute wrong results. The first sign is often NaN or infinite loss in a production run.
*   **Hung jobs:** An NCCL timeout, a stalled data pipeline, or a deadlock can stop a job without ending it. The job keeps its GPUs and their memory, and Slurm reports it as running until someone checks the loss curve or the log.
*   **Cluster-level failures:** Some failures happen in Kubernetes, not in a node's hardware. A device plugin crash-loops, a required DaemonSet never starts on a new node, or ranks on different nodes fall out of step in an NCCL collective. When the job fails, the error often doesn't say which pod or node caused it.

## 🛡️ New Infrastructure Checks
The health monitoring agent (HMA) watches each node for GPU errors, deep health checks test nodes during provisioning, and automatic node recovery reboots or replaces faulty hardware.

### Monitoring Agents and Checks
| Feature | Description |
| :--- | :--- |
| **Health Monitoring Agent (HMA)** | Watches each node for GPU errors such as Xid and NVLink faults, Elastic Fabric Adapter (EFA) errors, and kernel errors. |
| **MultiNodeTrainingValidation** | A new deep health check for HyperPod clusters orchestrated by Amazon Elastic Kubernetes Service (Amazon EKS). When HyperPod provisions an instance, or when you run the check on demand, it trains a small model on the instance and then across instances of the same type. The instance fails if the loss becomes NaN or infinite, or training doesn't finish in time. |
| **Kubernetes Resource Monitoring Agent** | Watches the Kubernetes layer of an EKS cluster for problems such as crash-looping device plugins, missing DaemonSets, and tainted nodes. When a job fails, it reports the pods and nodes involved as Kubernetes events and Amazon CloudWatch logs. |
| **Hung Job Detection** | Finds Slurm jobs that have stopped making progress. An agent on each node watches the job's output and GPU activity, or log patterns that you define. It writes an event to CloudWatch and can cancel the job so that Slurm requeues it. |

## ⚙️ Existing Resiliency Features
The existing HyperPod resiliency features check a single node at a time.

*   **InstanceStress:** Runs DCGM level 4 diagnostics and tests each instance's GPUs, GPU memory, NVLink, and EFA devices.
*   **InstanceConnectivity:** Runs NCCL tests across GPU instances, or NCCOM tests on AWS Trainium.

## 🚀 Availability
These checks run when instances are provisioned, or on demand, and confirm that their GPUs train correctly. Hung job detection runs alongside each Slurm job and catches a job that has stopped making progress.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22383-1-1.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/17/ML-22383-2-1.jpg)

#SageMakerHyperPod #MachineLearning #GPUComputing #Kubernetes #AWSInfrastructure

---

*Source: [Introducing workload recovery and expanded infrastructure checks on Amazon SageMaker HyperPod | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/introducing-workload-recovery-and-expanded-infrastructure-checks-on-amazon-sagemaker-hyperpod/)*
