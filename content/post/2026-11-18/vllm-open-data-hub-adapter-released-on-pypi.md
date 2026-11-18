---
title: "vLLM Open Data Hub Adapter Released on PyPi"
slug: "vllm-open-data-hub-adapter-released-on-pypi"
description: "A new adapter, vllm-tgis-adapter, has been made available on PyPi, facilitating the integration of vLLM with specific server infrastructure."
date: 2026-11-18T18:09:03+05:30
tags: [vLLM, Python, gRPC, DevTools, OpenDataHub]
categories: ["AI", "AI Infrastructure", "Developer Tools", "Model Serving", "Hardware Compatibility"]
image: "https://avatars.githubusercontent.com/u/57720972?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# vLLM Open Data Hub Adapter Released on PyPi

A new adapter, vllm-tgis-adapter, has been made available on PyPi, facilitating the integration of vLLM with specific server infrastructure.

## 📦 Installation and Monitoring

The package is distributed via PyPi. The installation process includes an additional tool that assists in monitoring the underlying services:
* Installing the adapter also installs a grpc healthcheck CLI.
* This CLI can be used to monitor the status of the grpc server.

## ⚙️ Server Configuration

The adapter interacts with a gRPC server environment:
* This will start serving a grpc server on port 8033.
* This can be queried with grpcurl.

## 🐳 Container Image

An image for deployment is available at:
* quay.io/opendatahub/vllm
* This image is built from opendatahub-io/vllm's Dockerfile.ubi.

## 🧪 Development and Testing Tools

The project utilizes specific tools for test automation and environment management:
* Nox is used to manage test automation.
* UV is used for venv management.
* The standard vllm built requires an Nvidia GPU.
* When this is not available, it is possible to compile vllm from source with CPU support.
* This makes it possible to run the tests on most hardware.
* Please note that the uv extra index url is required in order to install the torch CPU version.

#vLLM #Python #gRPC #DevTools #OpenDataHub

---

*Source: [opendatahub-io/vllm-tgis-adapter](https://github.com/opendatahub-io/vllm-tgis-adapter)*
