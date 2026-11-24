---
title: "Kubernetes v1.38 introduces breaking changes to WebSockets, cgroup drivers, and kubeconfig APIs"
slug: "kubernetes-v1-38-introduces-breaking-changes-to-websockets-cgroup-drivers-and-kubeconfig-apis"
description: "As the Kubernetes community approaches the v1.38 release, several deprecated features are being removed or deprecated to improve the project's long-term health and maintainability. These changes..."
date: 2026-11-24T18:09:57+05:30
tags: [Kubernetes, Containers, cgroups, Kubectl]
categories: ["AI", "Cloud Native", "Container Orchestration", "DevOps", "Infrastructure"]
author: "Shoubhik Banerjee"
draft: false
---

# Kubernetes v1.38 introduces breaking changes to WebSockets, cgroup drivers, and kubeconfig APIs

As the Kubernetes community approaches the v1.38 release, several deprecated features are being removed or deprecated to improve the project's long-term health and maintainability. These changes affect kubectl behavior, cgroup configuration, and API stability, requiring cluster administrators to update their configurations and scripts.

## 📡 Kubectl WebSockets Transition

Kubernetes has progressively moved kubectl from SPDY to WebSockets for exec, attach, and port-forward operations:

| Version | WebSocket Support |
|---------|-------------------|
| v1.30   | Default for exec, attach, cp operations |
| v1.31   | Default for port-forward operations |

The environment variables `KUBECTL_REMOTE_COMMAND_WEBSOCKETS` and `KUBECTL_PORT_FORWARD_WEBSOCKETS` were introduced to disable WebSocket usage. In v1.38, these variables will be removed. kubectl will always prefer WebSockets and fall back to SPDY when necessary. Scripts or CI environments that set these variables can remove them as they will no longer have any effect.

## ⚙️ Kubeconfig API Changes

The kuberc file manages kubectl user preferences and credential plugin allowlists. In the beta `kubectl.config.k8s.io/v1beta1` API, the `name` field served as an alias for `command`. The `name` field was deprecated in v1.36. With kuberc graduating to stable in v1.38, the new `kubectl.config.k8s.io/v1` API will not include `name`. Users with allowlist entries using `name` should update them to use `command`.

## 🔧 Container Runtime and cgroup Driver Updates

Support for cgroup v1 is being phased out. Since v1.35, kubelet fails to start on cgroup v1 nodes unless `failCgroupV1: false` is set in the kubelet configuration. This option remains in v1.38 but should be treated as a short-term workaround. Users are encouraged to migrate to cgroup v2.

Additionally, the legacy cgroup driver configuration mechanism is being deprecated. The kubelet will default to not allowing this mechanism in v1.38 and will require the container runtime to be running to query the recommended cgroup driver via CRI RuntimeConfig RPC. If the kubelet cannot retrieve the cgroup driver from the runtime after retrying, it will exit with an error before registering the node. The `cgroupDriver` field in the kubelet configuration file will be deprecated, and specifying it will be rejected unless the `LegacyCgroupDriverFallback` feature gate is enabled.

kubeadm will no longer default `cgroupDriver` to systemd and will report an error during preflight checks if the runtime doesn't support the RPC.

## 🌐 Admission Webhook Behavior Changes

Since v1.37, the `ExcludeAdmissionWebhookVirtualResources` feature gate is enabled by default. With this gate active, validating and mutating admission webhooks no longer receive requests for virtual resources like TokenReview, SelfSubjectReview, SubjectAccessReview, SelfSubjectAccessReview, and LocalSubjectAccessReview. Creating or updating a webhook configuration targeting these resources triggers a deprecation warning. Users relying on webhooks for these requests can disable the gate temporarily, but it is planned to be locked on when the feature graduates to stable.

## 💾 Resource Limit Enforcement for cgroup v2

On Linux nodes using cgroup v2 and configured with LimitedSwap, v1.38's kubelet will begin applying swap limits based on the Pod's memory settings.

## 🚀 Availability

These changes are planned for the Kubernetes v1.38 release. The information reflects the current status and may change before the actual release date.

#Kubernetes #Containers #cgroups #Kubectl

---

*Source: [Kubernetes v1.38 Sneak Peek](https://kubernetes.io/blog/2026/11/23/kubernetes-v1-38-sneak-peek/)*
