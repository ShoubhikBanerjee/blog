---
title: "Trynix Provides Browser-Based x86_64 Linux VMs via WebAssembly"
slug: "trynix-provides-browser-based-x86-64-linux-vms-via-webassembly"
description: "trynix.dev has launched a service that allows users to run an x86_64 Linux virtual machine entirely within a web browser using WebAssembly."
date: 2026-09-11T22:04:55+05:30
tags: [WebAssembly, Linux, Nix, VirtualMachine, GitHubActions]
categories: ["AI", "Virtualization", "Web Development", "Cloud Computing"]
author: "Shoubhik Banerjee"
draft: false
---

# Trynix Provides Browser-Based x86_64 Linux VMs via WebAssembly

trynix.dev has launched a service that allows users to run an x86_64 Linux virtual machine entirely within a web browser using WebAssembly.

## 🧩 How it works
* The service is powered by qemu-wasm.
* The virtual machines are URL addressable, allowing users to navigate to specific package links.
* There are no servers involved; the process runs only in browsers.

## ⚙️ Key details
* Users can boot the VM with any Nix package from the past 13 years.
* An interactive shell can be accessed by selecting a package (such as Python 3.6.2 from 2017) and clicking "Load".

## 🚀 Availability
* The service is available at trynix.dev.
* It introduces trynix-preview, a GitHub action that comments a link on a pull request, enabling users to boot the build of that PR in the browser via trynix.dev.

#WebAssembly #Linux #Nix #VirtualMachine #GitHubActions

---

*Source: [Any Nix package, live in your browser](https://simonwillison.net/2026/Sep/10/trynix/)*
