---
title: "OpenAI and Cisco Launch Open-Source Shirudo Security Tool"
slug: "openai-and-cisco-launch-open-source-shirudo-security-tool"
description: "OpenAI and Cisco launched an open-source Linux security tool named Shirudo. The tool deploys temporary runtime protections to block vulnerability exploitation while administrators prepare and roll..."
date: 2026-11-24T22:08:41+05:30
tags: [OpenAI, Cisco, LinuxSecurity, eBPF, Shirudo, RuntimeProtection]
categories: ["AI", "Cybersecurity", "Open Source", "AI Agents", "Infrastructure"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/24/Linux-shield.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI and Cisco Launch Open-Source Shirudo Security Tool

OpenAI and Cisco launched an open-source Linux security tool named Shirudo. The tool deploys temporary runtime protections to block vulnerability exploitation while administrators prepare and roll out patches, allowing operators to do so without restarting services.

## 🧩 How it works
Shirudo leverages the eBPF (extended Berkeley Packet Filter) mechanism in Linux to monitor for suspicious activity and deploy targeted protections called "shields." eBPF is a Linux technology that lets programs run in a controlled environment within the operating system's kernel without modifying its source code or requiring a restart.

The tool's capabilities include:
*   **Live protection:** Blocks vulnerable code paths without restarting systems, letting operators assess shield impact before enforcing them.
*   **AI-assisted defense:** Enables agents to investigate vulnerabilities, develop shields, and validate their effectiveness, with deployment remaining under human control.
*   **Trusted deployment:** Uses cryptographic signatures, Linux's eBPF verifier, and kernel security controls to prevent unauthorized modifications.
*   **Hardware-backed verification:** Uses Trusted Platform Modules (TPMs) to provide verifiable records of shields being loaded or removed.

Shirudo is designed for an agentic control plane with a configurable degree of autonomy when deploying mitigations. When a shield is deployed, the tool provides operators with hit counts, giving them insight into attempted exploits and where defenses need strengthening. Isovalent states that Shirudo is not limited to eBPF and can also modify application or userspace runtime bytecode to extend protection where needed.

## ⚙️ Key details
Shirudo is a rewrite of Tetragon, an open-source eBPF-based runtime security platform introduced by Isovalent in 2022. Tetragon also serves as the foundation for Cisco's existing Live Protect technology. Isovalent, a cloud networking and security company acquired by Cisco in 2024, developed the tool.

| Component | Description |
| :--- | :--- |
| Test Case | Researchers demonstrated that custom-generated shields could successfully block a Java4Shell exploit attempt against a running Elasticsearch service without interrupting its operation. |
| Distribution | Shields will be distributed as cryptographically signed ‘.bee’ packages through an OCI registry. |
| Execution | The tool can be activated through a command-line interface and doesn’t require a daemon to run permanently on the machine. |
| Compatibility | The tool's capabilities are limited to Linux because Mac and Windows have not implemented the components needed to be effective, according to Marcus Hutchins of Expel. |

The two companies plan to provide “ready-to-use” mitigations in the form of tested shields, along with vulnerability disclosures, until patching is possible. While there is "genuinely so much runtime exploit mitigation potential with eBPF," Marcus Hutchins noted that it may not be a good idea to let AI agents write rules that could impact the kernel.

## 🚀 Availability
Shirudo is open-source under BSD and GPL licenses. It comes with a quick-start guide as well as "getting started" documentation from Isovalent. On December 15, OpenAI will provide a technical rundown of how the tool works and how it combines eBPF and artificial intelligence to detect and counter new attacks in a deep-dive webinar.

The researchers state: "The Shirudo project is only the beginning, but it already shows the true potential of combining agents as a workforce with machine interfaces to let agents output what they are best at: code."

![figure](https://www.bleepstatic.com/c/w/AITR-Playbook.jpg)

#OpenAI #Cisco #LinuxSecurity #eBPF #Shirudo #RuntimeProtection

---

*Source: [New Shirudo tool uses AI to shield unpatched Linux systems from exploits](https://www.bleepingcomputer.com/news/security/new-shirudo-tool-uses-ai-to-shield-unpatched-linux-systems-from-exploits/)*
