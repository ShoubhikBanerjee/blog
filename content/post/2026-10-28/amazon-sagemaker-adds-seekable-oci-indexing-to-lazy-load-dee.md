---
title: "Amazon SageMaker adds Seekable OCI indexing to lazy‑load deep learning container images"
slug: "amazon-sagemaker-adds-seekable-oci-indexing-to-lazyload-deep-learning-container-images"
description: "Amazon SageMaker AI Training and Processing jobs now support Seekable OCI (SOCI) indexing, which removes the full container image download from the critical path and lets jobs start in seconds."
date: 2026-10-28T18:02:11+05:30
tags: [SageMaker, ContainerImages, SOCI, AWS, MLTraining]
categories: ["AI", "Machine Learning", "Cloud Computing", "DevOps", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-21882-featured-image-4.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon SageMaker adds Seekable OCI indexing to lazy‑load deep learning container images

Amazon SageMaker AI Training and Processing jobs now support Seekable OCI (SOCI) indexing, which removes the full container image download from the critical path and lets jobs start in seconds.

## 🔍 Overview
- "Every minute your deep learning container image spends downloading is a minute you pay for and a minute your team waits."
- "Container image download is pure overhead: billable job time that produces no model progress."
- "For modern deep learning images, that overhead is several minutes on every single job."
- "Today, we’re excited to announce Seekable OCI (SOCI) indexing for Amazon SageMaker AI Training and Amazon SageMaker AI processing jobs, which takes full container image download off the critical path of every job."

## 🧩 How it works
- "With SOCI indexing, SageMaker AI lazy‑loads your container image."
- "It fetches only the files needed to start the container and streams the rest in the background as your code runs, so your job begins in seconds instead of minutes."
- "Seekable OCI (SOCI) is an open source technology that lazy loads container images."
- "Instead of downloading the whole image before starting, the runtime uses a SOCI index to fetch only the files needed to launch the container immediately."
- "It then streams the rest in the background as your code accesses it."
- "A SOCI index is metadata that maps every file inside your image."
- "You store it in Amazon ECR as an OCI‑compliant artifact linked to your original image."
- "Because the index is a separate artifact, your image digest and any existing signatures remain valid."

## 📈 Measured results
- "As we show in the What we measured section, this reduced GPU idle time during image pulls by up to 90 percent in our benchmarks."
- "SOCI‑indexed images start Amazon SageMaker AI training containers in seconds, with no impact on training performance."

## ⚙️ Adoption
- "You adopt it by pointing to a pre‑indexed AWS Deep Learning Container (DLC) or adding an index to your own image."
- "Neither approach requires changes to your job definition, entry point, or data channels."
- "When you create a training or processing job, SageMaker AI checks whether the image you specified has a SOCI index and behaves accordingly:"
- "Because jobs always fall back to a standard download when needed, adding a SOCI index never prevents your job from running."
- "You only gain faster startup."
- "You never risk breaking an existing workflow."

## 💡 Why it matters
- "The result is faster job starts, lower job cost, and more time spent building models rather than waiting on infrastructure."
- "SageMaker AI training and processing jobs run inside container images stored in Amazon Elastic Container Registry (Amazon ECR)."
- "Before a job can execute your code, the service downloads the entire image to the instance."
- "It decompresses and writes every layer to disk."
- "For small images this takes seconds."
- "But deep learning images routinely exceed 10 GB or more."
- "That download adds minutes to every job, and you pay for it as job time."
- "The impact is largest exactly where iteration speed matters most: hyperparameter tuning sweeps for hundreds of jobs, quick experiments, and short processing jobs, where image download can dominate total runtime."
- "We pulled the same container images two ways on real SageMaker AI training jobs: standard download and SOCI‑indexed lazy loading."


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-21882-1-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-21882-2-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/ML-21882-3-2.png)

#SageMaker #ContainerImages #SOCI #AWS #MLTraining

---

*Source: [Announcing SOCI-indexed images for faster SageMaker AI jobs | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/announcing-soci-indexed-images-for-faster-sagemaker-ai-jobs/)*
