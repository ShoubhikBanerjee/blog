---
title: "Weaviate Helm Chart v17.1.0: Raft Bootstrap and Resource Limit Changes"
slug: "weaviate-helm-chart-v17-1-0-raft-bootstrap-and-resource-limit-changes"
description: "The Weaviate Helm chart has released version 17.1.0, introducing significant updates to cluster bootstrapping in Weaviate v1.25 and removing default resource constraints to improve module performance."
date: 2026-11-20T14:26:01+05:30
tags: [Weaviate, Kubernetes, Helm, VectorDB, DevOps]
categories: ["AI", "Vector Databases", "Cloud Infrastructure", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/37794290?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Weaviate Helm Chart v17.1.0: Raft Bootstrap and Resource Limit Changes

The Weaviate Helm chart has released version 17.1.0, introducing significant updates to cluster bootstrapping in Weaviate v1.25 and removing default resource constraints to improve module performance.

## 🔍 Overview

Weaviate can be deployed to a Kubernetes cluster using the provided Helm chart, provided that Helm is installed. Version 17.1.0 of the chart addresses specific infrastructure changes required by newer Weaviate releases and resolves performance restrictions in default configurations.

## ⚙️ Key Details: Cluster Bootstrapping

Weaviate v1.25 introduced a significant change in how the cluster bootstraps, driven by the adoption of a Raft-based consensus model.

*   The `podManagementPolicy` was changed from `OrderedReady` to `Parallel`.
*   This change is required for the Raft cluster to bootstrap properly, as all pods must start simultaneously.
*   Once the Raft cluster is established, rolling updates are possible.
*   This change takes effect when migrating from versions prior to v1.25 or when bootstrapping a new v1.25 cluster.

## ⚠️ Migration Steps

When upgrading from a version older than v1.25 to v1.25 or above, the following one-time operation is required:

1.  Delete Weaviate's Statefulset.
2.  Update the Statefulset settings to reflect the new policy.

This process will not remove your data but is necessary to make the update of Statefulset settings possible.

## 📉 Key Details: Resource Limits

In Weaviate-Helm version 17.1.0, the default resource limits and requests defined in the `values.yml` file have been removed.

*   **Reason:** Previous default values restricted the performance of some modules, making them almost unusable unless `resources.requests` and `resources.limits` were overridden.
*   **Impact:** Modules deployed with default values prior to version 17.1.0 will have their resource values removed upon upgrading to 17.1.0 or above, resulting in no constraints on memory or CPU usage.
*   **Recommendation:** To prevent modules from consuming all system resources, users are strongly recommended to override `modules.$MODULE.resources.requests` and `modules.$MODULE.resources.limits` with values that suit their specific system.

## 🛠 Release Process

To release a new version of the chart, the following steps are taken:

*   Bump the chart version in `./weaviate/Chart.yaml`.
*   Create a commit and an annotated tag matching the version number (prefixed with `v`, e.g., `v1.4.3`).
*   Push the commit and tag to the repository.
*   A GitHub Action creates a drafted release with the packaged chart attached.
*   The draft is edited to include release notes and published.

#Weaviate #Kubernetes #Helm #VectorDB #DevOps

---

*Source: [weaviate/weaviate-helm](https://github.com/weaviate/weaviate-helm)*
