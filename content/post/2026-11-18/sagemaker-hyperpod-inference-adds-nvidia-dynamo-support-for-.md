---
title: "SageMaker HyperPod Inference Adds NVIDIA Dynamo Support for Distributed AI"
slug: "sagemaker-hyperpod-inference-adds-nvidia-dynamo-support-for-distributed-ai"
description: "Amazon SageMaker HyperPod Inference now supports NVIDIA Dynamo, combining Dynamo’s distributed inference capabilities with the infrastructure management of HyperPod to address challenges such as..."
date: 2026-11-18T22:09:17+05:30
tags: [SageMaker, NVIDIA, Dynamo, Inference, DataPreparation]
categories: ["AI", "Machine Learning", "Infrastructure", "Data Engineering"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/14/ML-22230-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# SageMaker HyperPod Inference Adds NVIDIA Dynamo Support for Distributed AI

Amazon SageMaker HyperPod Inference now supports NVIDIA Dynamo, combining Dynamo’s distributed inference capabilities with the infrastructure management of HyperPod to address challenges such as GLM-5.3’s FP8 weights exceeding the 640 GB of GPU memory on a single ml.p5.48xlarge instance before accounting for KV cache and runtime overhead.

## 🧩 How it works
Dynamo is an open source distributed inference framework that supports multi-node deployment, disaggregated prefill and decode, and KV-aware routing with engines such as vLLM, SGLang, and TensorRT-LLM. HyperPod supports these deployments with high-performance Elastic Fabric Adapter (EFA) networking, coordinated GPU scheduling, and node health monitoring and recovery.

The HyperPod Inference add-on installs the Dynamo custom resource definitions and these serving and scheduling components:

*   **HyperPod Inference Operator**: Manages endpoint deployment through an InferenceEndpointConfig (IEC) custom resource, using its dynamoSpec section to supply the Dynamo configuration.
*   **Dynamo Operator**: Manages resources defined in a DynamoGraphDeployment (DGD), including the frontend, model workers, replica counts, and resource requirements.
*   **Grove**: Coordinates related groups of pods, including multi-node workers, and their scaling relationships.
*   **Kubernetes AI (KAI) Scheduler**: Places pods on GPU resources, using gang scheduling to schedule the pods required for a multi-node worker together.
*   **AWS Deep Learning Containers (DLCs)**: Provide the Dynamo runtime, while the add-on manages integrated component versions.

The Dynamo frontend routes requests to prefill workers, which process prompts, and decode workers, which generate tokens. These separate pools allow independent scaling and tuning. Both pools load the full model weights, and KV cache transfers between them over EFA. Dynamo also supports aggregated serving, where prefill and decode run in the same worker. In either topology, workers can run on one instance or span multiple instances using tensor and pipeline parallelism. Dynamo’s KV-aware router considers reusable prefix KV cache and active worker load in both topologies; prefix reuse can reduce prompt recomputation and improve time to first token, while load awareness helps avoid overloading workers.

## ⚙️ Key details
*   **Deployment Paths**: Deployments configured through InferenceEndpointConfig with dynamoSpec support invocation through SageMaker endpoints. Bring-your-own DynamoGraphDeployment (DGD) lets existing Dynamo users continue using upstream documentation, recipes, and manifests, with the Dynamo operator managing the deployment.
*   **Inference Engines**: You can choose vLLM, SGLang, or TensorRT-LLM, with vLLM used by default. The operator also supplies defaults for KV-aware routing and replica counts.
*   **Configuration**: Both paths support single-instance and multi-node deployments. Dynamo-specific settings belong under spec.dynamoSpec. For example, a configuration might run one model-worker replica across two instances (16 GPUs) with two frontend replicas for request handling. Setting dynamoSpec.frontend.routingMode to kv-aware turns on KV-aware routing.
*   **Health Management**: HyperPod provides node, GPU, and EFA health monitoring and manages node replacement, while the orchestration components recreate affected workers.

## 💡 Why it matters
For teams building specialized models, the hardest part is often finding enough task-specific data. Splunk, a Cisco company, faced exactly this when building evaluation models for its Agent Observability product. “For Splunk Agent Observability, our ability to train robust GenAI Eval models relies on access to high-quality, diverse datasets which are hard to curate for very specific tasks. Amazon SageMaker AI data preparation capabilities for synthetic data generation is meaningfully helping us scale these capabilities. We’ve been able to generate statistically representative synthetic datasets reliably and fast, while preserving the underlying patterns our models depend on. The seamless integration with the rest of our SageMaker workflow means our data scientists and customers spend less time wrangling data and more time building models that drive real enterprise value through Splunk.” — Yash Sheth, Director of Engineering, Splunk Agent Observability

Today, we’re expanding Amazon SageMaker AI with new AI data preparation capabilities for model development workflows. You can generate synthetic examples, assess and improve existing datasets, and bring expert feedback into the process through Python SDK APIs and the AWS AI-ML agent skill. With AI Data Preparation capabilities, you don’t need to stitch together labeling tools, generation scripts, and validation jobs. Each capability is a standalone building block that you can use on its own or chain together.

*   **Auto-labeling**: Label data at scale from an unlabeled dataset, a small labeled seed set, or no labels at all. Built-in task types include classification, named entity recognition, extractive question answering, ordinal rating, and summarization, and you can define custom tasks. For tasks with a fixed set of possible answers, a jury of several models labels each row, and their level of agreement becomes that row’s confidence score.
*   **Human Review**: Rows below your confidence threshold go to a review queue in Amazon SageMaker Studio, which uses the open-source Label Studio Community Edition. Reviewer corrections feed back into auto-labeling, and you can generate consensus metrics and labeling reports.
*   **Synthetic Data Generation**: Generate training, evaluation, and test data from a specification. You can ground the output in your own seed data and documents, and the service generates a code-based data generation pipeline that you can review, modify, reuse, and scale.
*   **Data Quality Evaluation**: Check datasets against your own business rules, built-in metrics, and LLM-as-a-judge metrics. Find duplicates and near-duplicates, and surface issues you didn’t think to check for, such as label noise or answer leakage.
*   **Data Transformation**: Clean and reshape data for your target training technique. Describe the change in plain language and have the code generated for you, use built-in operations such as dedupe, merge, split, and filter, or run your own Python at scale.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/14/ML-22230-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/14/ML-22230-2.png)

#SageMaker #NVIDIA #Dynamo #Inference #DataPreparation

---

*Source: [Managed NVIDIA Dynamo on Amazon SageMaker HyperPod Inference | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/managed-nvidia-dynamo-on-amazon-sagemaker-hyperpod-inference/)*
*Source: [Announcing AI data preparation capabilities in Amazon SageMaker: Build high-quality datasets for model development workflows | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/announcing-ai-data-preparation-capabilities-in-amazon-sagemaker-build-high-quality-datasets-for-model-development-workflows/)*
