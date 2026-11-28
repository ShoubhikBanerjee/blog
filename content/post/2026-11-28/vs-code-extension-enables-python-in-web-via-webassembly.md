---
title: "VS Code extension enables Python in Web via WebAssembly"
slug: "vs-code-extension-enables-python-in-web-via-webassembly"
description: "A new VS Code extension allows users to run Python code in the Web, such as in vscode.dev, using WebAssembly as the execution engine. The project is designed primarily as an experimentation..."
date: 2026-11-28T22:07:57+05:30
tags: [VSCode, WebAssembly, Python, Extension]
categories: ["AI", "Developer Tools", "Web Technologies", "Programming Languages"]
image: "https://avatars.githubusercontent.com/u/6154722?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# VS Code extension enables Python in Web via WebAssembly

A new VS Code extension allows users to run Python code in the Web, such as in vscode.dev, using WebAssembly as the execution engine. The project is designed primarily as an experimentation environment to help the VS Code team gain experience with running Python code in the Web using WebAssembly technologies.

## 🧩 How it works
The extension utilizes a pre-configured Python environment based on CPython WebAssembly builds, specifically the `Python-3.11.0rc1-wasm32-wasi-16.zip` build. It depends on the GitHub Repositories extension and requires users to authenticate with GitHub.

Users can set up their own Python environment, including source wheel Python packages, by following these steps:
- Create a new GitHub repository.
- Download a `wasm-wasi-16` build from the `tiran/cpython-wasm-test` releases and expand it into the root of the repository.
- To add source wheel packages, create a `site-packages` folder in the root.
- Install the package using the command `pip install my_package --target ./site-packages` (requires a local Python installation with pip).
- Commit the changes.
- Change the `python.wasm.runtime` setting to point to the user's GitHub repository.

## ⚙️ Key details
The extension is not intended for productive Python development due to several limitations:
- No pip support.
- No socket support.
- No support for native Python modules.
- No thread support.
- No async support, as a consequence of the lack of thread support.

Regarding versioning, odd major, minor, or patch version numbers indicate an insider or pre-release. For example, `1.0.0` and `0.1.0` are pre-releases, while `2.0.2` is a regular release. The initial version was 0.5.0, and version 0.7.0 added basic debugging support.

## 💡 Why it matters
This project serves as a testbed for integrating WebAssembly with Python in web-based development environments. It also outlines contribution requirements, noting that most contributions require agreeing to a Contributor License Agreement (CLA) to grant rights to use the contribution.

#VSCode #WebAssembly #Python #Extension

---

*Source: [microsoft/vscode-python-web-wasm](https://github.com/microsoft/vscode-python-web-wasm)*
