---
title: "Qdrant Helm Chart Enables Kubernetes Deployment with Community Support"
slug: "qdrant-helm-chart-enables-kubernetes-deployment-with-community-support"
description: "The Qdrant Helm chart has been introduced, enabling users to deploy Qdrant within their Kubernetes clusters. While distributed deployment is possible, the chart lacks advanced features found in..."
date: 2026-11-16T22:14:27+05:30
tags: [Kubernetes, Qdrant, Helm, AI]
categories: ["AI", "AI Infrastructure", "Cloud Computing", "Database Technologies", "Open Source"]
image: "https://avatars.githubusercontent.com/u/73504361?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Qdrant Helm Chart Enables Kubernetes Deployment with Community Support

The Qdrant Helm chart has been introduced, enabling users to deploy Qdrant within their Kubernetes clusters. While distributed deployment is possible, the chart lacks advanced features found in Qdrant Cloud and Private Cloud Enterprise Operator offerings.

## 📦 Deployment Options

The Helm chart is classified as open-source and provides a quick start for local or development environments. It installs the latest version of Qdrant by default.

## 🔧 Upgrade Process

Users can perform rolling upgrades using standard Helm commands:

```
helm repo update
helm upgrade your-qdrant-installation-name qdrant/qdrant
```

When a new Qdrant version is released, this procedure updates one node at a time. Any custom image tag overrides in `values.yaml` must be updated before executing the upgrade.

## ⚖️ Feature Comparison

A feature comparison table highlights differences between the Helm chart and Qdrant Cloud:

| Feature | Helm Chart | Qdrant Cloud |
|---------|------------|----------------|
| Zero-downtime upgrades | Limited | Full support |
| Monitoring, logging | Basic | Advanced |
| Backup and disaster recovery | Not included | Included |
| Enterprise support | Community only | Available |

Additional Qdrant Cloud capabilities include API keys with granular access control, data loss prevention on downscaling, automatic shard rebalancing, and full cluster backup functionality.

## 📚 Resources

For detailed configuration guidance, consult [the helm chart's README](charts/qdrant/README.md). Information about Qdrant Cloud deployment options is available at [Qdrant Cloud](https://qdrant.tech/cloud/).

#Kubernetes #Qdrant #Helm #AI

---

*Source: [qdrant/qdrant-helm](https://github.com/qdrant/qdrant-helm)*
