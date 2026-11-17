---
title: "Knowhere Provides Milvus’s C++ Vector Search Core"
slug: "knowhere-provides-milvuss-c-vector-search-core"
description: "Knowhere is an independent C++ project that serves as Milvus’s internal core for vector search, integrating FAISS, HNSW and DiskANN. It can be built as part of Milvus or developed as a library, with..."
date: 2026-11-17T18:10:30+05:30
tags: [Knowhere, Milvus, VectorSearch, C, CUDA]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Software Development", "Vector Databases"]
image: "https://avatars.githubusercontent.com/u/18416694?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Knowhere Provides Milvus’s C++ Vector Search Core

Knowhere is an independent C++ project that serves as Milvus’s internal core for vector search, integrating FAISS, HNSW and DiskANN. It can be built as part of Milvus or developed as a library, with CPU and GPU build options.

## 🔍 Overview

Knowhere acts as Milvus’s internal vector search engine. For users who want to use it within Milvus without modifying Knowhere’s source code, the project recommends building Milvus directly; Knowhere is then built implicitly.

## ⚙️ Platforms and dependencies

All Linux distributions are available for Knowhere development. Most contributors work on Ubuntu or CentOS, with a smaller group using Mac systems on x86_64 or Apple Silicon.

The project lists these verified operating systems for building and running Knowhere:

| Operating system | Details |
|---|---|
| Ubuntu 22.04 | x86_64 and Aarch64 |
| Ubuntu 20.04 | x86_64 and Aarch64; kept for legacy reasons, with EOL by April 2025 |
| macOS | x86_64 and Apple Silicon |

The `scripts/install_deps.sh` script installs dependencies for building, testing and shipping the Knowhere library.

## 🖥️ Build options

GPU support is disabled by default. Setting `WITH_GPU=True` enables Cardinal GPU support when building with Cardinal, or cuVS otherwise. `WITH_CUVS=True` explicitly enables cuVS, including alongside Cardinal, independently of `WITH_GPU`.

GPU builds use CUDA 13.2 for both cuVS and Cardinal. CMake prepares the toolkit before enabling CUDA, including when Knowhere is built through `add_subdirectory`. An existing toolkit at `/usr/local/cuda-13.2` is reused. If it is absent, `scripts/install_cuda.sh` installs it on Ubuntu 22.04 or 24.04, on x86_64 or Aarch64, and requires root access or passwordless sudo. Other systems must prepare the toolkit at that path beforehand. A GPU device or driver is not needed to compile, and the build must be reconfigured when switching CUDA versions. CPU builds do not invoke the CUDA installer.

Common build commands include:

| Build | Command |
|---|---|
| CPU release (default) | `make` |
| GPU release with cuVS | `make WITH_GPU=True` |
| GPU release with Cardinal | `make WITH_CARDINAL=True WITH_GPU=True` |
| CPU with unit tests | `make WITH_UT=True` |
| CPU unit tests with AddressSanitizer | `make WITH_UT=True WITH_ASAN=True` |
| GPU with unit tests | `make WITH_GPU=True WITH_UT=True` |
| Debug build | `make WITH_DEBUG=True` |
| C ABI and Java JNI bindings with C tests | `make WITH_JNI=True WITH_C_API_TESTS=True` |
| Custom compiler through a Conan profile | `make CONAN_PROFILE=clang14` |

Building a Python wheel requires `swig` and Python development headers, such as `python3-dev` on Ubuntu. A portable manylinux wheel can be built with `make wheel`.

## 🔌 Bindings and contributions

Optional C ABI and Java 11 JNI bindings expose indexes, brute-force search and named index blobs without a framework dependency. The Java bindings are documented in `java/README.md`.

Before submitting a pull request, contributors can install and enable pre-commit hooks with `pip3 install pre-commit` and `pre-commit install --hook-type pre-commit --hook-type pre-push`. They can run all hooks with `make pre-commit`, or run formatting and linting separately with `make format` and `make lint`. The lint command uses clang-tidy and requires a prior build. If clang-format and clang-tidy are not installed, the project provides installation instructions for Linux and Mac.

#Knowhere #Milvus #VectorSearch #C++ #CUDA

---

*Source: [zilliztech/knowhere](https://github.com/zilliztech/knowhere)*
