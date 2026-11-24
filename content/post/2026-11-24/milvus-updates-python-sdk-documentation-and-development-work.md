---
title: "Milvus Updates Python SDK Documentation and Development Workflow"
slug: "milvus-updates-python-sdk-documentation-and-development-workflow"
description: "The Milvus Vector Database project has released documentation and guidelines for its Python SDK, outlining installation methods, contribution processes, and version management practices."
date: 2026-11-24T12:08:32+05:30
tags: [Milvus, PythonSDK, VectorDatabase, DevOps, Programming]
categories: ["AI", "Database", "Developer Tools", "Software Engineering", "Data Infrastructure"]
image: "https://avatars.githubusercontent.com/u/51735404?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Milvus Updates Python SDK Documentation and Development Workflow

The Milvus Vector Database project has released documentation and guidelines for its Python SDK, outlining installation methods, contribution processes, and version management practices.

## 📦 Installation & Requirements
PyMilvus supports Python 3.9+ and can be installed via `pip` or `pip3`. Specific versions of PyMilvus can be installed or upgraded to the latest release using pip commands.

## 🛠️ Development Workflow
Local development for the project uses the `uv` package manager, which must be installed before running `make` targets. The process includes:
- Running pre-commit hooks to automatically execute linting and formatting checks before each commit.
- Retrieving protos matching generated files, with specific version details available in `milvus-proto`.

## 🔄 Testing & Versioning
Commits on the development branch are packaged and uploaded to Test PyPI. The package naming convention for development branches follows the format `x.y.z.rc<dist>`, where `<dist>` represents the number of commits differing from the most recent release. Installing these packages requires appending `--extra-index-url` to the pip command.

## 💬 Community & Documentation
Contributors are encouraged to read contribution guidelines before adding code. For discussions or problem-solving, the community can be reached in the Slack channel `#py-milvus`. Documentation for PyMilvus is available online at the project's API reference URL.

#Milvus #PythonSDK #VectorDatabase #DevOps #Programming

---

*Source: [milvus-io/pymilvus](https://github.com/milvus-io/pymilvus)*
