---
title: "OpenFold3 biomolecular structure prediction model available on Amazon SageMaker JumpStart"
slug: "openfold3-biomolecular-structure-prediction-model-available-on-amazon-sagemaker-jumpstart"
description: "The OpenFold Consortium and the AlQuraishi Lab at Columbia University have released OpenFold3-preview, an open-source, all-atom biomolecular structure prediction model. This research preview is now..."
date: 2026-11-14T12:02:58+05:30
tags: [OpenFold3, SageMaker, Bioinformatics, DrugDiscovery, AWS]
categories: ["AI", "Machine Learning", "Cloud Computing", "Life Sciences"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22226-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# OpenFold3 biomolecular structure prediction model available on Amazon SageMaker JumpStart

The OpenFold Consortium and the AlQuraishi Lab at Columbia University have released OpenFold3-preview, an open-source, all-atom biomolecular structure prediction model. This research preview is now available for deployment through Amazon SageMaker JumpStart.

## 🧩 How it works
OpenFold3 predicts the joint 3D structure of molecules from their sequences. Its capabilities include:

* Protein folding for multi-chain protein complexes
* Folding of protein-nucleic acid assemblies
* Modeling of protein-ligand complexes
* Single-molecule structure prediction for proteins, DNA, RNA, and small-molecule ligands

## ⚙️ Key details
Computational drug discovery teams can use this model for target identification, antibody and protein engineering, and structure-based virtual screening. Because structure prediction tasks can take minutes, the deployment utilizes asynchronous inference:

* Requests are uploaded to Amazon S3 and processed via InvokeEndpointAsync.
* The endpoint supports an invocation timeout of up to 1 hour.
* Results or error details are written back to a user-specified S3 location.
* The system handles internal request queuing and scales to zero instances when the queue is empty to avoid idle costs.

## 🚀 Availability
OpenFold3 is released under the Apache 2.0 license, allowing organizations to inspect, fine-tune, and build upon the model. Users can deploy the model into their own AWS account using a few lines of code. The deployment runs in an AWS-maintained container with network isolation to maintain data privacy.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22226-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22226-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/12/ML-22226-3.png)

#OpenFold3 #SageMaker #Bioinformatics #DrugDiscovery #AWS

---

*Source: [OpenFold3 on Amazon SageMaker JumpStart: Predict biomolecular structures | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/openfold3-on-amazon-sagemaker-jumpstart-predict-biomolecular-structures/)*
