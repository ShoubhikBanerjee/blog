---
title: "GS Caltex Automates Handoff Between SageMaker Canvas and SageMaker Pipelines"
slug: "gs-caltex-automates-handoff-between-sagemaker-canvas-and-sagemaker-pipelines"
description: "GS Caltex has implemented an automated workflow that connects machine learning models built in Amazon SageMaker Canvas to production environments via Amazon SageMaker Pipelines. This update..."
date: 2026-11-14T12:02:58+05:30
tags: [AWS, SageMaker, MLOps, GS_Caltex, Automation]
categories: ["AI", "Machine Learning", "MLOps", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21878-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# GS Caltex Automates Handoff Between SageMaker Canvas and SageMaker Pipelines

GS Caltex has implemented an automated workflow that connects machine learning models built in Amazon SageMaker Canvas to production environments via Amazon SageMaker Pipelines. This update streamlines the collaboration between process engineers, who design no-code models, and machine learning (ML) engineers, who manage production deployment and monitoring.

## 🔍 Overview
The integration addresses previous requirements for manual work when moving assets between environments. In the updated workflow, process engineers use their domain expertise to build and validate models in SageMaker Canvas without writing code. ML engineers then configure the necessary workflows to automate model deployment and scheduled inference.

## 🧩 How it works
The machine learning operations (MLOps) workflow at GS Caltex now follows two distinct paths: preparing new model versions and running batch inference. 

*   **Model Preparation:** Process engineers prepare data visually and build models. Validated assets are registered in the Amazon SageMaker Model Registry.
*   **Automated Handoff:** ML engineers receive the preprocessing flow and model to review data formats. They use a separate handoff process that converts these assets into executable SageMaker Pipelines steps.
*   **Production Execution:** ML engineers configure input and output paths and schedule runs through Amazon EventBridge. SageMaker Pipelines then extracts input data from Amazon S3, runs preprocessing logic, and executes SageMaker Batch Transform.

## ⚙️ Key details
The technical roles and components involved in the automated workflow are summarized below:

| Component | Function |
| :--- | :--- |
| Amazon SageMaker Canvas | Enables visual data preparation and no-code model building for process engineers. |
| Amazon SageMaker Pipelines | Reuses preprocessing logic and trained models to run production workflows. |
| Amazon SageMaker Model Registry | Stores model versions and manages the approval process for deployment. |
| Amazon S3 | Stores preprocessing flows, input data for batch inference, and results. |
| Amazon EventBridge | Triggers pipeline runs every 30 minutes for scheduled batch inference. |

## 💡 Why it matters
The automation of the handoff process has significantly accelerated GS Caltex's deployment cycles. ML engineers are now able to deploy models within a few hours, a process that previously took approximately one week. Additionally, by running batch inference every 30 minutes instead of utilizing continuously running endpoints, the company has meaningfully lowered its inference costs. The system also improves monitoring, as ML engineers can inspect step status and CloudWatch logs to track the health of the production pipeline.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21878-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/10/ML-21878-2.png)

#AWS #SageMaker #MLOps #GS_Caltex #Automation

---

*Source: [Production MLOps at GS Caltex with Amazon SageMaker Canvas, part 1 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/production-mlops-at-gs-caltex-with-amazon-sagemaker-canvas-part-1/)*
*Source: [Build a model improvement flywheel with Amazon SageMaker HyperPod Data Capture | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-model-improvement-flywheel-with-amazon-sagemaker-hyperpod-data-capture/)*
