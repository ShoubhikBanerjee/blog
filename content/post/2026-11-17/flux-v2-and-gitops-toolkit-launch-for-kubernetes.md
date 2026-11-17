---
title: "Flux v2 and GitOps Toolkit Launch for Kubernetes"
slug: "flux-v2-and-gitops-toolkit-launch-for-kubernetes"
description: "Flux version 2 (v2) has been released, built from the ground up to use the Kubernetes API extension system. It integrates with the GitOps Toolkit, a set of composable APIs and specialized tools..."
date: 2026-11-17T22:09:21+05:30
tags: [Kubernetes, GitOps, ContinuousDelivery, Flux, CNCF]
categories: ["AI", "DevOps", "Cloud Computing", "Kubernetes"]
image: "https://avatars.githubusercontent.com/u/52158677?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Flux v2 and GitOps Toolkit Launch for Kubernetes

Flux version 2 (v2) has been released, built from the ground up to use the Kubernetes API extension system. It integrates with the GitOps Toolkit, a set of composable APIs and specialized tools designed for building continuous delivery on top of Kubernetes.

## 🔍 Overview
Flux is an open and extensible continuous delivery solution for Kubernetes that keeps clusters in sync with sources of configuration, such as Git repositories and OCI artifacts. It automates updates to configuration when there is new code to deploy. The project is a Cloud Native Computing Foundation (CNCF) graduated project, used in production by various organizations and cloud providers.

## 🧩 How it works
The GitOps Toolkit consists of the APIs and controllers that make up the runtime for Flux v2. These APIs comprise Kubernetes custom resources, which can be created and updated by cluster users or other automation tooling. Flux v2 is constructed to integrate with Prometheus and other core components of the Kubernetes ecosystem.

## ⚙️ Key details
Version 2 introduces several long-requested features, including:
- Support for multi-tenancy
- Ability to sync an arbitrary number of Git repositories
- Extensibility through the composable APIs of the GitOps Toolkit

Users can use the toolkit to extend Flux or to build custom systems for continuous delivery.

## 🚀 Availability
To get started, users can refer to the available guide on how to bootstrap Flux on Kubernetes and deploy a sample application in a GitOps manner. Developer guides are also available for those wishing to build their own systems using the toolkit.

#Kubernetes #GitOps #ContinuousDelivery #Flux #CNCF

---

*Source: [fluxcd/flux2](https://github.com/fluxcd/flux2)*
