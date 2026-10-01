---
title: "NVIDIA Announces cuObject General Availability and Expands xio-sig Partnership"
slug: "nvidia-announces-cuobject-general-availability-and-expands-xio-sig-partnership"
description: "NVIDIA has announced the general availability of cuObject client and server libraries and is expanding xio-sig to include cuObject alongside cuFile in partnership with Microsoft and Google Cloud."
date: 2026-10-01T22:03:23+05:30
tags: [NVIDIA, GPU, ObjectStorage, RDMA, cuObject]
categories: ["AI", "AI Infrastructure", "Cloud Storage", "Hardware Acceleration"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/AI-Storage-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Announces cuObject General Availability and Expands xio-sig Partnership

NVIDIA has announced the general availability of cuObject client and server libraries and is expanding xio-sig to include cuObject alongside cuFile in partnership with Microsoft and Google Cloud.

## 🧩 How it works

SCADA serves as the software infrastructure supporting high-throughput, fine-grained, GPU-initiated storage access. This system enables compute accelerators—including GPUs, TPUs, and XPUs—to utilize remote direct memory access (RDMA) via NIC- or DPU-accelerated data transfers, such as NVIDIA ConnectX NIC or NVIDIA BlueField DPU.

This architecture allows AI accelerators to access file and object storage without routing data through the server CPU, resulting in:
* Higher throughput
* Lower latency
* Reduced CPU utilization for data reads and writes

## ⚙️ Key details

Through the NVIDIA Storage-Next initiative, NVIDIA is leading a group of over 40 vendors and customers—including hyperscalers, application developers, controller vendors, NAND vendors, and storage providers—to define GPU-driven storage and establish interoperable, open industry standards.

| Component | Function |
| :--- | :--- |
| **cuObject** | Provides APIs and an RDMA wire protocol for building accelerated object-storage applications and servers. |
| **xio-sig** | Provides a path for the cuObject client to interoperate with any server-side implementation adhering to the wire protocol. |
| **SCADA Server SDK** | Enables storage providers to build servers that respond to GPU-initiated requests from SCADA clients. |
| **Storage Lender Service** | Part of the effort accompanying the SCADA command-line utility for configuration and deployment. |

## 💡 Why it matters

The general availability of cuObject libraries offers standardized methods for accelerated AI data access using both object and file protocols for storage consumers, storage providers, open source framework developers, and AI application developers.

Interoperability efforts include:
* **IBM:** Demonstrated a prototype integrating SCADA and IBM Storage Scale, where a SCADA client sends requests to a Storage Scale SCADA server built with the new SDK.
* **Google Cloud:** A maintainer for cuFile in xio-sig, Google Cloud is evaluating expanding its participation for cuObject.
* **Microsoft:** Planning to join the xio-sig Board to improve storage I/O interoperability.

## 🚀 Availability

* cuObject client and server libraries are generally available.
* cuObject Server 2.0.0 and NVIDIA CUDA 13.4 preview downloads are available.
* Repository structures are established for cuFile and cuObject; headers, the cuObject wire protocol, and library implementation code (libxFile and xFilekernel) will be shared after the production-ready stack passes conformance tests.
* Governance documents are currently under review by pending Board Members.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/figure-1-3.webp)

#NVIDIA #GPU #ObjectStorage #RDMA #cuObject

---

*Source: [Expanding AI Storage Access with NVIDIA cuObject and the NVIDIA SCADA Server SDK | NVIDIA Technical Blog](https://developer.nvidia.com/blog/expanding-ai-storage-access-with-nvidia-cuobject-and-the-nvidia-scada-server-sdk/)*
