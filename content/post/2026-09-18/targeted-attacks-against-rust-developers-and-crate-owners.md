---
title: "Targeted Attacks Against Rust Developers and Crate Owners"
slug: "targeted-attacks-against-rust-developers-and-crate-owners"
description: "Adam Harvey and the crates security team have issued a warning regarding an ongoing campaign targeting rust-lang members and owners of popular crates to compromise devices and accounts for the..."
date: 2026-09-18T06:03:39+05:30
tags: [Rust, Cybersecurity, SupplyChainAttack, OpenSource]
categories: ["AI", "Cybersecurity", "Software Development", "Open Source"]
author: "Shoubhik Banerjee"
draft: false
---

# Targeted Attacks Against Rust Developers and Crate Owners

Adam Harvey and the crates security team have issued a warning regarding an ongoing campaign targeting rust-lang members and owners of popular crates to compromise devices and accounts for the purpose of publishing malware.

## 🧩 How it works
Attackers use video calls framed as positive opportunities—such as projects, jobs, or contract opportunities—as a vector to:
* Get the target to install software on their computer (e.g., a purportedly missing audio codec).
* Get the target to execute a command (e.g., via a command placed on the clipboard).

## ⚙️ Key details
* **Impact:** Last month, this method was used in a successful supply chain attack against the array ref crate and others.
* **Risk Factor:** Every piece of software depending on open source has a network of human beings who are potential attack vectors, specifically anyone with publishing rights to packages in the dependency network.
* **Defense:** A recommended defense is the use of dependency cooldowns, which involves waiting a few days before upgrading to new package releases to allow others to spot supply chain attacks.

#Rust #Cybersecurity #SupplyChainAttack #OpenSource

---

*Source: [Be alert: targeted attacks on prominent Rustaceans](https://simonwillison.net/2026/Sep/17/targeted-attacks-on-rustaceans/)*
