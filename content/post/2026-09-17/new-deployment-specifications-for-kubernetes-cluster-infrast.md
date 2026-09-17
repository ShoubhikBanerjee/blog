---
title: "New Deployment Specifications for Kubernetes Cluster Infrastructure"
slug: "new-deployment-specifications-for-kubernetes-cluster-infrastructure"
description: "A new infrastructure deployment specification has been released, supporting highly available clusters across a wide range of cloud providers and Linux distributions."
date: 2026-09-17T06:05:39+05:30
tags: [Kubernetes, CloudInfrastructure, Linux, DevOps]
categories: ["AI", "Cloud Computing", "Infrastructure", "Software Development"]
image: "https://avatars.githubusercontent.com/u/36015203?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Deployment Specifications for Kubernetes Cluster Infrastructure

A new infrastructure deployment specification has been released, supporting highly available clusters across a wide range of cloud providers and Linux distributions.

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

The system supports most popular Linux distributions, including:
* Debian Bookworm, Trixie
* Ubuntu 22.04, 24.04, 26.04
* CentOS Stream / RHEL 9, 10
* Fedora 39, 40, 41, 42
* Fedora CoreOS
* openSUSE Leap 16.x/Tumbleweed
* Oracle Linux 9, 10
* Alma Linux 9, 10
* Rocky Linux 9, 10 (experimental in 10)
* Flatcar Container Linux by Kinvolk
* Kylin Linux Advanced Server V10 (experimental)
* Amazon Linux 2 (experimental)
* UOS Linux (experimental)
* openEuler (experimental)

**Note:** Upstart/SysV init based OS types are not supported.

### Component Versions

| Component | Version |
| :--- | :--- |
| kubernetes | 1.36.4 |
| etcd | 3.6.14 |
| docker | 28.3 |
| containerd | 2.3.5 |
| cri-o | 1.36.5 (experimental; Fedora, Ubuntu, and CentOS based OS only) |
| cni-plugins | 1.9.1 |
| calico | 3.31.7 |
| cilium | 1.20.2 |
| flannel | 0.28.9 |
| kube-ovn | 1.12.21 |
| kube-router | 2.1.1 |
| multus | 4.2.2 |
| kube-vip | 1.0.3 |

## 🧩 How it works

* **Composable:** Users have a choice of the network plugin for instances.
* **Testing:** The system utilizes continuous integration tests.

#Kubernetes #CloudInfrastructure #Linux #DevOps

---

*Source: [kubernetes-sigs/kubespray](https://github.com/kubernetes-sigs/kubespray)*
