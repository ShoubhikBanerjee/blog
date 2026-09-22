---
title: "Positron IDE Now Available on Amazon SageMaker AI"
slug: "positron-ide-now-available-on-amazon-sagemaker-ai"
description: "Positron, an integrated development environment for data science, is now available to run on Amazon SageMaker AI. Platform administrators can deploy Positron by building a container image based on..."
date: 2026-09-22T22:03:42+05:30
tags: [Positron, SageMaker, AWS, DataScience, MachineLearning]
categories: ["AI", "Machine Learning", "Cloud Computing", "Data Science", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/18/ML-21876-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Positron IDE Now Available on Amazon SageMaker AI

Positron, an integrated development environment for data science, is now available to run on Amazon SageMaker AI. Platform administrators can deploy Positron by building a container image based on the Amazon SageMaker Distribution and attaching it to a SageMaker Studio domain.

## 🧩 How it works

Positron operates within a Space on SageMaker, allowing teams to reserve capacity for scheduled training. Within this environment, users can leverage the Space execution role to query Amazon Athena, the AWS Glue Data Catalog, and Amazon S3 directly. Users have the ability to run multiple independent Spaces simultaneously or share a single Space for collaboration.

## ⚙️ Key details

* **AI Integration:** Posit Assistant, the AI coding assistant, integrates with Amazon Bedrock. This allows AI operations to run within your own AWS account and Region, ensuring customer content is encrypted and not used to improve base models.
* **Workflow Management:** The IDE supports a complete data science lifecycle, including project exploration, R and Python session management, variable tracking, terminal access, and application previews.
* **Security:** Private connectivity can be configured using AWS PrivateLink.

## 💡 Demonstration Workflow

| Component | Function |
| :--- | :--- |
| Amazon S3 | Stores source data |
| AWS Glue Data Catalog | Registers source data |
| Amazon Athena | Queries data |
| R | Validates features |
| Python | Trains XGBoost classifier |
| Shiny for Python | Invokes deployed endpoint |
| Quarto | Records the workflow |

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/18/ML-21876-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/18/ML-21876-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/18/ML-21876-3.png)

#Positron #SageMaker #AWS #DataScience #MachineLearning

---

*Source: [Run Positron on Amazon SageMaker AI for data science workflows | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/run-positron-on-amazon-sagemaker-ai-for-data-science-workflows/)*
