---
title: "Kubernetes Mutating Webhook Released for Automated Sidecar Injection"
slug: "kubernetes-mutating-webhook-released-for-automated-sidecar-injection"
description: "A new Kubernetes mutating webhook has been developed to automate the injection of sidecar containers into pod specifications. This tool simplifies the management of sidecars within a Kubernetes..."
date: 2026-11-20T06:16:59+05:30
tags: [Kubernetes, Sidecar, DevOps, Containers, Automation]
categories: ["AI", "Cloud Infrastructure", "Software Development", "DevOps"]
image: "https://avatars.githubusercontent.com/u/38541875?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Kubernetes Mutating Webhook Released for Automated Sidecar Injection

A new Kubernetes mutating webhook has been developed to automate the injection of sidecar containers into pod specifications. This tool simplifies the management of sidecars within a Kubernetes cluster.

## 🧩 How it works
To trigger an injection, users must add an annotation—defaulting to `sidecar-injector.expedia.com/inject`—to the target pod specification, including the name of the ConfigMap that defines the sidecar configuration.

## ⚙️ Key details
* Sidecar Scope: Applications are limited to accessing sidecars within their own namespaces.
* Namespace Watching: By default, the webhook monitors all namespaces except `kube-system` and `kube-public`.
* Configurability: Namespace monitoring settings can be adjusted via Helm values.

## 🚀 Availability
Deployment is supported through two methods:
* Helm: Files located in `deployment/helm`.
* kubectl: Files located in `deployment/kubectl`.

To use the Helm method, users must add the repository to their Helm repositories. Those interested in contributing to the codebase are encouraged to review the developer documentation for building and testing procedures.

#Kubernetes #Sidecar #DevOps #Containers #Automation

---

*Source: [ExpediaGroup/kubernetes-sidecar-injector](https://github.com/ExpediaGroup/kubernetes-sidecar-injector)*
