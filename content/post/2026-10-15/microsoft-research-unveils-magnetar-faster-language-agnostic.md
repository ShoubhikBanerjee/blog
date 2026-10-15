---
title: "Microsoft Research unveils Magnetar: Faster, language‑agnostic zero‑knowledge proofs"
slug: "microsoft-research-unveils-magnetar-faster-languageagnostic-zeroknowledge-proofs"
description: "Magnetar is the newest zero‑knowledge proof system from Microsoft Research. It can prove the correct execution of programs written in Rust, Go, or C, runs 10 to 39 times faster than earlier..."
date: 2026-10-15T22:04:06+05:30
tags: [ZeroKnowledge, Cryptography, MicrosoftResearch, VerifiableComputing]
categories: ["AI", "Cryptography", "Computer Security", "Software Engineering"]
image: "https://www.microsoft.com/en-us/research/wp-content/uploads/2026/10/Magnetar-TWLIFB-1200x627-1.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft Research unveils Magnetar: Faster, language‑agnostic zero‑knowledge proofs

Magnetar is the newest zero‑knowledge proof system from Microsoft Research. It can prove the correct execution of programs written in Rust, Go, or C, runs 10 to 39 times faster than earlier comparable systems, and its security relies only on standard hash functions.

## 🔍 Overview
- Runs a workload and produces, together with the output, a short cryptographic proof that the program ran correctly.
- The proof is small and can be checked in milliseconds by anyone, without rerunning the program, without trusting the prover, and without needing the input data.
- Verification can be passed on to others who need the same assurance.

## 🧩 How it works
- Zero‑knowledge proofs allow a prover to convince a verifier that a computation was performed correctly while revealing nothing about private inputs.
- Magnetar’s processor description builds on the Phalanx idea of exploiting repetition in a processor’s instruction cycle to accelerate proof generation.
- The system is instantiated with hash‑based cryptographic primitives, eliminating the need for a trusted setup and avoiding elliptic‑curve‑based constructions.

## ⚙️ Key details
- **Supported languages:** Rust, Go, C.
- **Performance:** 10 to 39 times faster on average than the prior fastest comparable systems.
- **Proof size and verification:** Proofs are short; verification takes milliseconds.
- **Security basis:** Relies only on standard hash functions, not on elliptic curves.
- **Zero‑knowledge property:** The proof reveals no information about inputs that should stay private.

## 📚 Background
- Zero‑knowledge proofs were invented in the 1980s; the concept of proving program execution has been around nearly as long.
- Early practical approaches were limited to small programs and required either a layered sum‑check protocol or elliptic‑curve cryptography with a trusted setup.
- In 2019, the Spartan system returned to the sum‑check approach, supporting general‑purpose programs without a trusted setup and allowing different cryptographic building blocks.
- Phalanx (2021) demonstrated how to use repeated processor steps to achieve an order‑of‑magnitude speed improvement over Spartan.
- Magnetar is the latest result of more than a decade of research at Microsoft Research on making zero‑knowledge proofs practical.

## 🔐 Security & Quantum Considerations
- Many prior proof systems rest on elliptic curves, which can be broken by sufficiently powerful quantum computers.
- Microsoft’s Quantum Safe Program aims to move products and services to post‑quantum cryptography by 2029.
- Post‑quantum proof systems exist but often rely on newer cryptographic functions that have not undergone decades of scrutiny.
- Magnetar’s reliance on standard hash functions avoids the unproven assumptions of newer primitives.


![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/10/Magnetar-BlogHeroFeature-1400x788-1-1024x576.jpg)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/10/Magnetar_NEW_Summary_Simple.png)

![figure](https://uhf.microsoft.com/images/microsoft/RE1Mu3b.png)

#ZeroKnowledge #Cryptography #MicrosoftResearch #VerifiableComputing

---

*Source: [Magnetar brings faster, simpler, quantum-ready zero-knowledge proofs](https://www.microsoft.com/en-us/research/blog/proof-based-general-purpose-computing-with-magnetar/)*
