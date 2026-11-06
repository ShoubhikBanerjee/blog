---
title: "Proof‑Driven Development introduced with PDD Kit and Verus for Rust"
slug: "proofdriven-development-introduced-with-pdd-kit-and-verus-for-rust"
description: "Proof‑Driven Development (PDD) arrives as a new software‑development paradigm supported by **PDD Kit**.  The toolkit helps teams turn their intent into formal specifications, automatically proves the..."
date: 2026-11-06T06:03:11+05:30
tags: [ProofDrivenDevelopment, FormalVerification, AIcodingAgents, Rust]
categories: ["AI", "Software Engineering", "Artificial Intelligence", "Formal Methods", "Programming Languages"]
image: "https://www.microsoft.com/en-us/research/wp-content/uploads/2026/10/PDDKitRecap-TWLIFB-1200x627-1.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Proof‑Driven Development introduced with PDD Kit and Verus for Rust

Proof‑Driven Development (PDD) arrives as a new software‑development paradigm supported by **PDD Kit**.  The toolkit helps teams turn their intent into formal specifications, automatically proves the generated code for every input, and falls back to tests when a proof cannot reach.

## 🔍 Overview
- Coding agents can now generate whole features that span tens of thousands or hundreds of thousands of lines of code.
- Traditional line‑by‑line review does not scale to this output, and tests often only check what the agent built, not what was originally requested.
- A *plan* is meant to be the contract between a developer and an agent, but the agent is not forced to obey it, leading to hidden gaps that surface only as bug reports or edge‑case failures.

## 🧩 How it works
1. **Intent → Formal Spec** – PDD Kit works with you to express the parts of your intent that can be formalized as a specification in **Verus**.
2. **Proof Generation** – The kit automatically generates a mathematical proof that the agent’s code satisfies the formal spec for every possible input.
3. **Fallback to Tests** – Anything the proof cannot reach (e.g., third‑party cryptography libraries, UI code) is turned into informal specifications and covered by high‑quality unit, end‑to‑end, terminal‑automation, and browser‑automation tests.
4. **TCB Sign‑off** – The boundary between proved code and tested code is the Trusted Computing Base (TCB). PDD Kit makes this line explicit and asks the developer to sign off on each piece.
5. **Collaboration Environment** – The workflow runs inside **GitHub Next’s Chopin**, a real‑time, multiplayer planning environment where teams and agents can co‑author a shared document.

## ⚙️ Key details
- **PDD Kit** – the toolkit that drives the Proof‑Driven Development process.
- **Verus** – the verifier used today; a proof language for Rust co‑developed by Microsoft Research, Carnegie Mellon University, VMware Research, ETH Zurich, MPI‑SWS, UNSW Sydney, the University of Texas at Austin, the University of Michigan, the University of British Columbia, the University of Wisconsin–Madison, and the Weizmann Institute of Science.
- **Chopin** – the planning interface that lets a team and agents iterate on the plan and proposed tests before handing off implementation.
- **Formal verification** – a mathematical proof that code satisfies its specification for every input, providing stronger assurance than testing alone.
- **Evidence vs. Proof** – a passing test is labeled as evidence; only a verifier‑checked proof guarantees correctness for all inputs.
- **Real‑world case** – inside Chopin, PDD Kit was used to formally verify the login logic of **Pet Store**, a Rust storefront. Verus hardened the code, uncovered existing bugs, and proved the absence of login bugs with respect to the specification.

## 💡 Why it matters
- Proofs cover the entire input space, catching bugs that a test suite—no matter how large—might miss.
- By making the TCB explicit, teams understand exactly which pieces rely on trust and can review them separately.
- The approach scales to agent‑generated code where traditional code review is infeasible.
- It bridges the gap between the plan (the contract) and the shipped code, reducing the hidden mismatch that typically appears only after deployment.

## 📊 Components at a glance
| Component | Role |
|-----------|------|
| PDD Kit | Turns intent into formal specs, generates proofs and tests |
| Verus | Verifier that checks Rust code against formal specs |
| Chopin (GitHub Next) | Real‑time, multiplayer planning environment for teams and agents |



![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/11/fig01-pipeline_NEW_PDD-Kit.png)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/11/fig07-proof-boundary_NEW_PDD-Kit-scaled.png)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/11/fig04-intent-map_NEW_PDD-Kit.png)

#ProofDrivenDevelopment #FormalVerification #AIcodingAgents #Rust

---

*Source: [Formally verifying agent-written full-stack web apps with PDD Kit - Microsoft Research](https://www.microsoft.com/en-us/research/blog/formally-verifying-agent-written-full-stack-web-apps-with-pdd-kit/)*
