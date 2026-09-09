---
title: "Asqav Releases Python and TypeScript SDKs for AI Agent Evidence"
slug: "asqav-releases-python-and-typescript-sdks-for-ai-agent-evidence"
description: "Asqav has released Python and TypeScript SDKs to provide verifiable evidence of AI agent actions through an evidence layer."
date: 2026-09-09T12:04:45+05:30
tags: [AIagents, SDK, Cryptography, Compliance, PostQuantum]
categories: ["AI", "AI Agents", "Software Development", "Cybersecurity"]
image: "https://avatars.githubusercontent.com/u/32335502?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Asqav Releases Python and TypeScript SDKs for AI Agent Evidence

Asqav has released Python and TypeScript SDKs to provide verifiable evidence of AI agent actions through an evidence layer.

## 🔍 Overview

The SDKs enable AI agents to generate signed, hash-chained compliance receipts for every action. These receipts are timestamped against independent witnesses and can be verified by auditors, regulators, or counterparties without an Asqav account.

## 🧩 How it works

* **Cryptography**: Server-side cryptography is used, meaning there are zero native dependencies in either SDK. 
* **Algorithms**: The algorithm used is per-receipt from `signature.alg`, utilizing ML-DSA-65 (FIPS 204, post-quantum) for cloud-issued receipts and Ed25519/ES256 for locally signed ones.
* **Verification**: 
    * Users with a `signature_id` can verify without an API key.
    * The `verify()` function returns a public verdict and recomputes the `chain_hash` locally as the SHA-256 over the RFC 8785 canonical payload.
    * Offline, zero-trust checks that reproduce the signature can be performed via `asqav.verify_receipt_offline(receipt, jwks)` in Python, `verifyReceiptOffline()` in TypeScript, or a standalone CLI command: `python -m asqav.verifier.verify_receipt --offline`.

## ⚙️ Key details

| Component | Details |
| :--- | :--- |
| **Python SDK** | `pip install asqav` (Requires Python 3.10+); tested on 3.10, 3.11, 3.12 |
| **TypeScript SDK** | `npm install @asqav/sdk` (Requires Node 20.19-20.x or 22.12+); tested on Node 20, 22 |
| **Integrations** | Works with LangChain, CrewAI, and MCP |
| **Diagnostics** | `asqav doctor` validates configuration and connectivity when `ASQAV_API_KEY` is set |

## 🚀 Availability

Asqav offers three plans:
* **Free**: No credit card required.
* **Pro**: Paid monthly or annual subscription.
* **Enterprise**: Custom and volume-priced.

This development is profiled in the IETF Internet-Draft `draft-marques-asqav-compliance-receipts` and the Independent Submission profiling `draft-farley-acta-signed-receipts`.

#AIagents #SDK #Cryptography #Compliance #PostQuantum

---

*Source: [jagmarques/asqav-sdk](https://github.com/jagmarques/asqav-sdk)*
