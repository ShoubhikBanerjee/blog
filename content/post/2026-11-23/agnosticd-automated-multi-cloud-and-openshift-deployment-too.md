---
title: "AgnosticD: Automated Multi‑Cloud and OpenShift Deployment Tool"
slug: "agnosticd-automated-multicloud-and-openshift-deployment-tool"
description: "AgnosticD is a fully automated two‑phase deployer that can provision basic infrastructure and deliver fully configured application environments on public cloud providers or OpenShift clusters."
date: 2026-11-23T22:18:20+05:30
tags: [AgnosticD, Ansible, OpenShift, Automation, Cloud]
categories: ["AI", "DevOps", "Cloud Computing", "Automation", "OpenShift"]
image: "https://avatars.githubusercontent.com/u/21339385?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AgnosticD: Automated Multi‑Cloud and OpenShift Deployment Tool

AgnosticD is a fully automated two‑phase deployer that can provision basic infrastructure and deliver fully configured application environments on public cloud providers or OpenShift clusters.

## 🔍 Overview
- Fully automated 2‑Phase deployer for infrastructure and application environments.
- Works with public Cloud Providers **and** OpenShift clusters.
- Not limited to OpenShift deployment, but frequently used for OpenShift workloads.

## 🧩 How it works
- Uses Ansible playbooks; the main entry point is `main.yml` in the `./ansible` directory.
- Each **Config** bundles five sequential deployment playbooks plus supporting files.
- Configs combine with cloud‑provider tools such as `awscli` to create infrastructure through to running applications.
- For OpenShift workloads, AgnosticD runs an Ansible role (`ocp‑workload‑*`) against an existing OpenShift cluster; roles are version‑agnostic and work across OpenShift 3 and 4.
- Execution can be containerised using the project’s supported images for reproducibility.

## ⚙️ Key details
| Environment / Example | Description |
|---|---|
| Just a bunch of nodes | Simple, multi‑cloud deployment of a set of generic Linux hosts. |
| Three Tier App | Deploys a basic three‑tier application, defaulting to a set of Linux hosts ready for configuration. |
| OCP4 Cluster | Deploys a fully installed OpenShift 4 cluster onto AWS, OpenStack, etc. |
| API as a Business demo | Deploys a workload (e.g., 3Scale) onto an existing OpenShift cluster or a local instance; one of ~30 ready‑to‑go OpenShift workloads. |

- Roles directory contains the `ocp‑workload‑*` roles.
- Configs directory holds user‑defined environments that can be abstracted for AWS, Azure, and other public or private clouds.

## 🚀 Availability
- Documentation provides guides for creating OpenShift workloads and custom configs.
- Container images are provided for reproducible runs.
- Video introduction and first OSP environment walkthrough are available as learning resources.

## 💡 Why it matters
- Enables consistent, repeatable deployments across heterogeneous cloud environments.
- Supports both infrastructure provisioning and application configuration in a single workflow.
- Allows teams to reuse existing OpenShift workloads across versions without modification.
- Abstracted configs simplify multi‑cloud strategies, reducing operational overhead.

#AgnosticD #Ansible #OpenShift #Automation #Cloud

---

*Source: [redhat-cop/agnosticd](https://github.com/redhat-cop/agnosticd)*
