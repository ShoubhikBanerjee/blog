---
title: "boxd Launches Self-Hosted Isolated MicroVMs for AI Agents and Developers"
slug: "boxd-launches-self-hosted-isolated-microvms-for-ai-agents-and-developers"
description: "A new self-hosted solution called boxd provides fast, isolated machines for AI agents and development teams to use as sandboxes, dev environments, or servers. The platform runs in your own Google..."
date: 2026-11-20T14:26:01+05:30
tags: [AIagents, CloudComputing, DevOps, MicroVMs]
categories: ["AI", "AI Infrastructure", "AI Agents", "Cloud Computing"]
image: "https://avatars.githubusercontent.com/u/349490272?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# boxd Launches Self-Hosted Isolated MicroVMs for AI Agents and Developers

A new self-hosted solution called boxd provides fast, isolated machines for AI agents and development teams to use as sandboxes, dev environments, or servers. The platform runs in your own Google Cloud project, AWS account, or on bare metal servers you already run, providing teams with a dedicated console, CLI, and API.

## 🔍 Overview

The platform allows teams to run fast microVMs that can be forked and snapshotted. Key features and capabilities include:

* **Flexible environments**: MicroVMs can be used as agent sandboxes, development environments, or servers in the sizes you pick.
* **Network accessibility**: Every VM is reachable over HTTPS and SSH, with support for custom domains and raw TCP or UDP ports.
* **AI Agent integration**: The CLI comes with a built-in agent skill for Claude Code, Codex, and OpenCode.
* **Broad authentication**: Users can sign in with Google or GitHub, or via single sign-on through Entra ID, Okta, Google Workspace, or Keycloak.
* **Secured ingress**: Supports private ingress on AWS, where no node has a public IP and users reach the cluster over a VPN.
* **Pricing**: The platform is free for up to 16 worker vCPUs.

## ⚙️ How it works

The open-source installer sets up a complete boxd cluster from a single configuration file (`cluster.toml`) with one command. The only requirement on the local machine is Docker. The install script runs tested versions of Terraform, Ansible, gcloud, and the AWS CLI inside a Docker image. 

Installation takes about an hour, with most of the time spent running the 20- to 40-minute apply process. Before any software is unpacked, the installer downloads and checks signed release binaries against release-keys. The cluster state, including TLS keys and provider secrets, is kept encrypted in a bucket you own (or in a local file next to `cluster.toml` for bare metal).

## 🧩 Cluster Architecture

A boxd cluster is composed of multiple node roles. While one node can have several roles, default examples put all roles except the worker on a single control node and add a single worker.

| Node Role | Description |
| :--- | :--- |
| **Control nodes** | Run the cluster's state over raft. |
| **Workers** | Run the microVMs under KVM on boxd's own host kernel. |
| **Proxy** | Connects every VM to the internet at https://<name>.<zone> and over SSH. |
| **Console** | Serves the web console, the API, and a pre-configured CLI. |
| **DNS node** | Answers for your registered DNS zone. |
| **Metrics node** | Stores the graphs that are displayed for each VM in the console. |

#AIagents #CloudComputing #DevOps #MicroVMs

---

*Source: [boxd-sh/self-host](https://github.com/boxd-sh/self-host)*
