---
title: "AWS Launches Generative AI Starter Kit for Amazon EKS"
slug: "aws-launches-generative-ai-starter-kit-for-amazon-eks"
description: "AWS has introduced a comprehensive toolkit for deploying production-ready Generative AI infrastructure on Amazon EKS. This starter kit is designed for teams running self-hosted LLMs and AI workloads..."
date: 2026-11-20T12:08:10+05:30
tags: [AWS, GenerativeAI, AmazonEKS, LLMs, AIWorkloads]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Machine Learning", "DevOps"]
image: "https://avatars.githubusercontent.com/u/8931462?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Launches Generative AI Starter Kit for Amazon EKS

AWS has introduced a comprehensive toolkit for deploying production-ready Generative AI infrastructure on Amazon EKS. This starter kit is designed for teams running self-hosted LLMs and AI workloads on AWS.

## 🔍 Overview
- A comprehensive toolkit for deploying production-ready Generative AI infrastructure on Amazon EKS.
- Includes pre-configured components for AI Gateway (LiteLLM), LLM Serving (vLLM, SGLang, Ollama), Vector Databases, Embedding Models (TEI), Observability (Langfuse, Phoenix), etc.
- Built for teams running self-hosted LLMs and AI workloads on AWS.

## ⚙️ Key details
- Deploy LLM serving engines (vLLM, SGLang, TGI), AI gateways, vector databases, GPU-accelerated inference platforms, and AI agent frameworks on Kubernetes with a single CLI command.
- The starter kit includes the configurable components and examples from several categories:
  - AI Gateway - LiteLLM, Kong AI Gateway OSS
  - LLM Model - vLLM, SGLang, Ollama
  - Embedding Model - Text Embedding Inference (TEI)
  - Observability (o11y) - Langfuse, Phoenix
  - GUI App - Open WebUI
  - Vector Database - Qdrant, Chroma, Milvus
  - Workflow Automation - n8n
  - AI Agent - OpenClaw
  - MCP Server - FastMCP 2.0
  - AI Agent Framework - Strands Agents, Agno

## 🚀 Availability
- Before you begin, ensure you have the following tools installed: AWS CLI, Terraform, Node.js, kubectl, Helm, Docker and Buildx.
- To quickly set up a demo environment with infrastructure and essential components and examples: `./cli demo-setup`.
- For a more customized setup, you can use the interactive setup command: `./cli interactive-setup`.
- This starter kit supports deploying NVIDIA Dynamo for optimized LLM inference on Amazon EKS.
- `./cli nvidia-platform monitoring install` # Prometheus + Grafana
- `./cli nvidia-platform gpu-operator install` # NVIDIA GPU Operator
- `./cli nvidia-platform dynamo-platform install` # Dynamo CRDs, Operator, etcd, NATS
- `./cli nvidia-platform dynamo-vllm install` # Deploy a model with vLLM

## 💡 Why it matters
- This starter kit simplifies the deployment of production-ready Generative AI infrastructure on Amazon EKS, making it easier for teams to run self-hosted LLMs and AI workloads on AWS.
- The inclusion of various pre-configured components and examples allows for a more customized and efficient setup.
- The support for NVIDIA Dynamo ensures optimized LLM inference, enhancing the performance of AI workloads.

#AWS #GenerativeAI #AmazonEKS #LLMs #AIWorkloads

---

*Source: [aws-samples/sample-genai-on-eks-starter-kit](https://github.com/aws-samples/sample-genai-on-eks-starter-kit)*
