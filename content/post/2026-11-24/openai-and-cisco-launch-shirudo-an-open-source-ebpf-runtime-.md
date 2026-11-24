---
title: "OpenAI and Cisco launch Shirudo, an open-source eBPF runtime for Linux security"
slug: "openai-and-cisco-launch-shirudo-an-open-source-ebpf-runtime-for-linux-security"
description: "OpenAI and Cisco are launching Shirudo, an open-source runtime designed to help teams protect Linux systems while they roll out patches. The tool is built to assist security teams in managing the..."
date: 2026-11-24T06:12:57+05:30
tags: [OpenAI, Cisco, eBPF, Cybersecurity, Linux, OpenSource]
categories: ["AI", "Cybersecurity", "Linux", "Open Source", "AI Agents"]
image: "https://images.ctfassets.net/kftzwdyauwt9/5K7gFDr3r8vgjdIcsW6RVY/aba5325ce7902e5d1499b907f8e78f0b/shirudo-partner-logos-landscape-2x.png?w=1600&h=900&fit=fill"
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI and Cisco launch Shirudo, an open-source eBPF runtime for Linux security

OpenAI and Cisco are launching Shirudo, an open-source runtime designed to help teams protect Linux systems while they roll out patches. The tool is built to assist security teams in managing the tradeoff between immediate protection and long-term patching by using eBPF, a Linux technology that allows small programs to run at specific points inside the operating system.

## 🧩 How it works
Shirudo uses eBPF to observe suspicious activity and apply targeted security protections to running systems without requiring a restart. The system enables "live protection," where eBPF shields can block vulnerable code paths while applications continue to run.

- **Agent Integration**: OpenAI and Cisco are designing Shirudo to give AI agents programmable controls to investigate vulnerabilities, develop targeted shields, and validate their effectiveness against exploits and real workloads.
- **Pre-enforcement Monitoring**: Security teams can monitor how a proposed shield would affect applications before enforcing it.
- **Vulnerability Specifics**: In a controlled test, a Codex-generated shield blocked a Java4Shell exploit attempt against a running Elasticsearch service. The shield added an input check to Java's Base64 decoder and attached it directly to the process, rejecting malicious input while the service continued running.

## ⚙️ Security and verification
The platform includes multiple layers of verification and control to ensure integrity and safety:

- **Signed Shields**: Shields are cryptographically signed and verified before loading.
- **Kernel Safety**: Linux's eBPF verifier checks eBPF programs against safety rules, while kernel security controls restrict unauthorized changes.
- **Hardware Attestation**: Shirudo uses a Trusted Platform Module (TPM) to support a verifiable record of protections being loaded or removed, allowing operators to check whether systems meet their security requirements.
- **Least Privilege**: Applications run with only the permissions they need, governed by policies that are automatically generated and maintained.

## 🚀 Availability and licensing
OpenAI and Cisco are open-sourcing Shirudo to allow developers, security researchers, and infrastructure operators to inspect the code, test protections, and contribute to its development.

- **License**: BSD 2-Clause (with BPF programs dual-licensed under BSD and GPL).
- **Goal**: The team aims to make tested shields available alongside vulnerability disclosures, giving operators a way to evaluate and deploy temporary protections while preparing permanent patches.
- **Resources**:
  - A VM quickstart guide is available to sign, load, and verify a test protection.
  - Isovalent offers a self-guided lab to explore the technology.
  - A technical deep-dive webinar is scheduled for December 15.

## 💡 Why it matters
The long-term goal is to enable defenders and AI agents to quickly identify affected systems, validate protections, and deploy eBPF shields that block exploits without disrupting workloads. By combining hardware-backed attestation and independent network controls, the system provides additional assurance even if individual systems are compromised, ensuring that permanent patches can be prepared while maintaining operational continuity.

![figure](https://images.ctfassets.net/kftzwdyauwt9/bScTLq9smNJq5XAlaHIQW/fab0e70b1aab8ca8dffb70a747056fd7/guardian-agent-desktop-light.png?w=3840&q=90&fm=webp)

#OpenAI #Cisco #eBPF #Cybersecurity #Linux #OpenSource

---

*Source: [OpenAI and Cisco introduce Shirudo](https://openai.com/index/introducing-shirudo/)*
