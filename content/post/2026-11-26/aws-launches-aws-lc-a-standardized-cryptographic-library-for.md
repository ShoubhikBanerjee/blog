---
title: "AWS Launches AWS-LC, a Standardized Cryptographic Library for PQC"
slug: "aws-launches-aws-lc-a-standardized-cryptographic-library-for-pqc"
description: "AWS has released AWS‑LC, a unified cryptographic library that supports post‑quantum algorithms while maintaining compatibility, assurance, and performance."
date: 2026-11-26T06:13:08+05:30
tags: [Cryptography, PostQuantum, AWSLC, Security]
categories: ["AI", "Security", "Cloud Computing", "Cryptography"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2025/06/11/main-2841.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Launches AWS-LC, a Standardized Cryptographic Library for PQC

AWS has released AWS‑LC, a unified cryptographic library that supports post‑quantum algorithms while maintaining compatibility, assurance, and performance.

## 🔍 Overview
- AWS‑LC is a general‑purpose cryptographic library maintained by AWS.
- Derived from BoringSSL, which originated from OpenSSL.
- It provides hybrid post‑quantum key exchange via s2n‑tls for service endpoints.
- It underlies aws‑lc‑rs (Rust), rustls, and the Amazon Corretto Crypto Provider (Java).
- AWS‑LC keeps an OpenSSL‑compatible API so applications can replace algorithms without rewriting.
- AWS uses it across its services; if you've called an AWS API, AWS‑LC was used on the server side.

## 🧩 How it Works
- AWS‑LC uses formal verification to prove selected algorithm implementations correct.
- It optimizes algorithm implementations to reduce latency and compute costs of new algorithms.
- For TLS, AWS‑LC libssl keeps an OpenSSL‑compatible API; most applications that use OpenSSL for TLS build against it with small changes.
- Applications that call libcrypto directly may need more work, as the API differs in places.
- When new algorithms are added, s2n‑tls, s2n‑quic, aws‑lc‑rs, and the Amazon Corretto Crypto Provider adopt them automatically.
- Hybrid ML‑KEM key exchange is enabled through existing TLS configuration APIs.
- 1Password used AWS‑LC to move clients to hybrid post‑quantum key exchange with only a one‑line Cargo.toml change and no application code changes.

## ⚙️ Key Details
- Three properties that reduce cost and friction of cryptographic updates:
  - Compatibility: update doesn't require application changes.
  - Assurance: new code can be trusted when it ships.
  - Performance: new algorithm doesn't add much computational overhead or latency.
- AWS‑LC long‑term support (LTS) releases keep a stable application binary interface (ABI).
- Applications link once, then take library updates without a rebuild.
- One update reaches every application on the host when each process restarts.

## 🚀 Availability
- AWS‑LC is available as an AWS‑LC library for C/C++.
- The Rust bindings are available via aws‑lc‑rs.
- Java integration is available via Amazon Corretto Crypto Provider.

## 💡 Why It Matters
- Every cryptographic algorithm has an expiration date; traditional ones like MD5 and SHA‑1 have been retired.
- Standards are revised and flaws found in implementations.
- PQC is accelerating the pace of adding new algorithms and removing old ones to keep up with regulations and risk.
- The move to PQC has government and regulator deadlines; PQC will progress in phases to enable hybrid and pure post‑quantum algorithms.
- Each change reaches systems as a software library update; the practical question is how often you can roll out a new version and its cost.
- By standardizing on a single library like AWS‑LC, organizations reduce ongoing responsibility and operational risk.

## 📊 Performance Impact
- TLS1.3 setup time on Graviton4 is measured for different algorithms; the figure shows impact of new algorithms.
![TLS1.3 Setup Time](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/figure2-tls13-setup-time-by-algorithm-graviton4.png)

- Client‑server architecture using hybrid ML‑KEM.
![Client-Server ML-KEM](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/figure1-alt-client-server-ml-kem-768-ml-dsa-87-graviton4.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/figure1-alt-client-server-ml-kem-768-ml-dsa-87-graviton4.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/25/figure2-tls13-setup-time-by-algorithm-graviton4.png)

#Cryptography #PostQuantum #AWSLC #Security

---

*Source: [Make post-quantum cryptography updates routine with AWS-LC | Amazon Web Services](https://aws.amazon.com/blogs/security/make-post-quantum-cryptography-updates-routine-with-aws-lc/)*
