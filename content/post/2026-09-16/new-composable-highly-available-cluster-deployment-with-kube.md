---
title: "New Composable Highly Available Cluster Deployment with Kubernetes 1.36.4"
slug: "new-composable-highly-available-cluster-deployment-with-kubernetes-1-36-4"
description: "A new composable, highly available cluster has been introduced, supporting a wide range of cloud environments, bare metal deployments, and popular Linux distributions."
date: 2026-09-17T00:50:10+05:30
tags: [Kubernetes, CloudComputing, Linux, Infrastructure]
categories: ["AI", "Cloud Infrastructure", "DevOps", "Containerization"]
image: "https://avatars.githubusercontent.com/u/36015203?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Composable Highly Available Cluster Deployment with Kubernetes 1.36.4

A new composable, highly available cluster has been introduced, supporting a wide range of cloud environments, bare metal deployments, and popular Linux distributions.

## 🚀 Availability

The system can be deployed on the following platforms:
* AWS
* GCE
* Azure
* OpenStack
* vSphere
* Equinix Metal (bare metal)
* Oracle Cloud Infrastructure (Experimental)
* Baremetal

## ⚙️ Key details

### Supported Operating Systems

The cluster supports most popular Linux distributions, though Upstart/SysV init based OS types are not supported. Support includes:

| OS Family | Supported Versions |
| :--- | :--- |
| Ubuntu | 22.04, 24.04, 26.04 |
| Fedora | 39, 40, 41, 42 |
| Debian | Bookworm, Trixie |
| CentOS Stream / RHEL | 9, 10 |
| Alma Linux | 9, 10 |
| Rocky Linux | 9, 10 (experimental in 10) |
| Oracle Linux | 9, 10 |
| openSUSE | Leap 16.x/Tumbleweed |
| Specialized | Flatcar Container Linux by Kinvolk, Fedora CoreOS |
| Experimental | Kylin Linux Advanced Server V10, Amazon Linux 2, UOS Linux, openEuler |

### Technical Stack

The deployment utilizes the following components and versions:

* **Core:** kubernetes 1.36.4, etcd 3.6.14
* **Container Runtimes:** docker 28.3, containerd 2.3.5, cri-o 1.36.5 (experimental; available only on Fedora, Ubuntu, and CentOS based OS)
* **Networking & Plugins:** cni-plugins 1.9.1, calico 3.31.7, cilium 1.20.2, flannel 0.28.9, kube-ovn 1.12.21, kube-router 2.1.1, multus 4.2.2, kube-vip 1.0.3
* **Management & Tools:** cert-manager 1.15.3, coredns 1.14.2, argocd 2.14.5, helm 3.18.4, metallb 0.13.9, registry 2.8.1

## 🧩 How it works

* **Composable Architecture:** Users have a choice of the network plugin for instances.
* **Quality Assurance:** The system utilizes continuous integration tests.

#Kubernetes #CloudComputing #Linux #Infrastructure

---

*Source: [kubernetes-sigs/kubespray](https://github.com/kubernetes-sigs/kubespray)*
