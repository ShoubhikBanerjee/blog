---
title: "Bridgecrew launches Checkov for IaC and Open‑Source Package Security Scanning"
slug: "bridgecrew-launches-checkov-for-iac-and-opensource-package-security-scanning"
description: "Bridgecrew introduced Checkov, a static code analysis tool for infrastructure‑as‑code (IaC) that also performs software composition analysis (SCA) on container images and open‑source packages,..."
date: 2026-10-11T18:05:47+05:30
tags: [Checkov, IaC, SCA, CloudSecurity]
categories: ["AI", "Cloud Security", "Infrastructure As Code", "Software Composition Analysis", "DevSecOps"]
image: "https://avatars.githubusercontent.com/u/48174253?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Bridgecrew launches Checkov for IaC and Open‑Source Package Security Scanning

Bridgecrew introduced Checkov, a static code analysis tool for infrastructure‑as‑code (IaC) that also performs software composition analysis (SCA) on container images and open‑source packages, helping developers prevent cloud misconfigurations and discover vulnerabilities early in the build process.

## 🔍 Overview
- Checkov scans cloud infrastructure provisioned with Terraform, Terraform plan, CloudFormation, AWS SAM, Kubernetes, Helm charts, Kustomize, Dockerfile, Serverless, Bicep, OpenAPI, ARM Templates, or OpenTofu.
- It also scans open‑source packages and images for Common Vulnerabilities and Exposures (CVEs).
- The tool powers Prisma Cloud Application Security, the developer‑first platform that codifies and streamlines cloud security throughout the development lifecycle.

## 🧩 How it works
- Uses graph‑based scanning to provide context‑awareness policies.
- Supports Python format for attribute policies and YAML format for both attribute and composite policies.
- Detects AWS credentials in EC2 Userdata, Lambda environment variables, and Terraform providers.
- Identifies secrets using regular expressions, keywords, and entropy‑based detection.

## ⚙️ Supported platforms
| Category | Supported Types |
|---|---|
| IaC templates | Terraform, Terraform plan, Terraform JSON, CloudFormation, AWS SAM, Kubernetes, Helm, Kustomize, Dockerfile, Serverless framework, Ansible, Bicep, ARM, OpenTofu |
| CI pipelines | Argo Workflows, Azure Pipelines, BitBucket Pipelines, Circle CI Pipelines, GitHub Actions, GitLab CI workflow files |

## 📋 Key Features
- Over 1 000 built‑in policies covering security and compliance best practices for AWS, Azure, and Google Cloud.
- Scans both IaC files and CI workflow definitions.
- Performs Software Composition Analysis (SCA) for images and open‑source packages.
- Provides context‑aware, graph‑based detection.
- Enables policy authoring in Python and YAML.

## 🔐 Detection capabilities
- Finds misconfigurations in IaC and cloud resources.
- Detects AWS credentials in various locations.
- Identifies secrets using regex, keywords, and entropy detection.
- Scans container images and open‑source packages for CVEs.

## 🚀 Availability
- Checkov is integrated into Prisma Cloud Application Security, delivering continuous security for cloud resources and IaC throughout the development lifecycle.

#Checkov #IaC #SCA #CloudSecurity

---

*Source: [bridgecrewio/checkov](https://github.com/bridgecrewio/checkov)*
