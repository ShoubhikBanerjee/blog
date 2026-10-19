---
title: "Push‑based NIXL connector speeds up vLLM inference on AWS EFA"
slug: "pushbased-nixl-connector-speeds-up-vllm-inference-on-aws-efa"
description: "vLLM’s new push‑based NVIDIA Inference Xfer Library (NIXL) connector reduces transfer latency between prefill and decode stages, delivering up to 3× faster first‑token latency and 30 % lower..."
date: 2026-10-19T22:04:08+05:30
tags: [vLLM, NIXL, AWS]
categories: ["AI", "Machine Learning", "Inference Engineering", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21812-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Push‑based NIXL connector speeds up vLLM inference on AWS EFA

vLLM’s new push‑based NVIDIA Inference Xfer Library (NIXL) connector reduces transfer latency between prefill and decode stages, delivering up to 3× faster first‑token latency and 30 % lower time‑per‑output‑token on AWS instances.

## 🔍 Overview
- **vLLM** is an open‑source inference and serving engine for large language models.
- It separates *prefill* and *decode* into separate engine instances (prefill‑decode disaggregation) so each phase can scale and be optimized independently.
- KV‑block data moves between instances via the **NIXL connector**, which exploits RDMA‑capable interconnects such as **AWS Elastic Fabric Adapter (EFA)**.
- The default NIXL mode is *pull‑based*; the new *push‑based* mode moves coordination off the critical path.

## 🧩 How the push‑based connector works
- Three actors are coordinated:
  1. **Decode instance** registers its target blocks in advance while the prefill instance is still computing KV.
  2. **Prefill instance** matches each request and issues the transfer.
  3. A **background thread** carries the KV write off the engine’s forward‑pass loop.
- Registration (identity + block locations) is sent as an NIXL notification during the same engine step.
- Transfer starts when the later of two events occurs (registration arrival or prefill completion).
- Requests are paired by ID; the matching logic handles reissued, preempted, or retried requests.
- Once matched, the producer opens a connection (if needed) and issues an NIXL **WRITE** that copies KV blocks directly into the decoder’s registered memory, addressing each tensor‑parallel rank.
- Producer and consumer may use different internal block layouts; each side maps block locations to its own physical layout at transfer time, allowing different block sizes.
- Each WRITE includes a completion notification.

## ⚙️ Key technical details
- NIXL moves KV blocks over interconnects that support **Remote Direct Memory Access (RDMA)**, avoiding host‑memory staging.
- On supported instance types, **AWS EFA** provides **GPUDirect RDMA** and **Neuron Direct RDMA**.
- The push mode removes the serialization inherent in the pull model by overlapping producer and consumer work.
- Transfer‑setup time runs on the prefill side and on a background thread, not on the decode instance.

## 🚀 Performance
| Mode | TTFT improvement | TPOT improvement |
|------|------------------|-----------------|
| Pull (default) | baseline | baseline |
| Push (new) | up to **3×** faster | up to **30 %** faster |

- Benchmarks were run on a **1P1D** deployment using **Amazon EC2 P5en** instances connected with EFA.
- Model: **Qwen3‑32B**.
- The same push‑mode gains were observed on **AWS Trainium** clusters and on GPU clusters, confirming accelerator‑agnostic benefits.

## 💡 Why it matters
- Direct KV block transfer between device memories reduces latency and improves throughput for large language model serving.
- Overlapping coordination with computation maximizes utilization of high‑performance interconnects such as EFA.
- The feature is contributed back to the open‑source vLLM project, making it available to any deployment that can use RDMA‑capable networking.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21812-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21812-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/15/ML-21812-3.png)

#vLLM #NIXL #AWS

---

*Source: [Push-based KV transfer to improve TTFT and TPOT for disaggregated inference in vLLM | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/push-based-kv-transfer-to-improve-ttft-and-tpot-for-disaggregated-inference-in-vllm/)*
