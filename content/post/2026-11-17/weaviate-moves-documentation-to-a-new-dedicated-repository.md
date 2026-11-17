---
title: "Weaviate Moves Documentation to a New Dedicated Repository"
slug: "weaviate-moves-documentation-to-a-new-dedicated-repository"
description: "The documentation for the Weaviate project has been moved to a new repository at `weaviate/docs` and is now live at https://docs.weaviate.io. The updated documentation platform uses Docusaurus 2, a..."
date: 2026-11-17T22:09:21+05:30
tags: [Weaviate, Docusaurus, OpenSource, Documentation]
categories: ["AI", "Developer Tools", "Open Source", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/37794290?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Weaviate Moves Documentation to a New Dedicated Repository

The documentation for the Weaviate project has been moved to a new repository at `weaviate/docs` and is now live at https://docs.weaviate.io. The updated documentation platform uses Docusaurus 2, a static website generator running under Node.js, and uses the yarn project management tool to manage dependencies.

## ⚙️ Key details

The documentation build system leverages several tools and configuration specifications:

* **Docusaurus 2**: A static website generator running under Node.js that builds the site and generates static content into the `build` directory.
* **Node.js**: Installed via the `nvm` package manager. While `nvm` installs the most recent version of Node.js by default, contributors should install the version specified in `.github/workflows/pull_requests.yaml` (which is version 20 at the time of writing).
* **Yarn & npm**: The `npm` package manager, which is included with Node.js, is used to install `yarn`. In turn, `yarn` is used to install Docusaurus and manage project dependencies.
* **Code Formats**: Code examples in the documentation are presented in one of two formats, with many utilizing a custom `FilteredTextBlock` JSX component.

## 🧩 How to Contribute

Contributors can update the documentation by setting up a local development environment and submitting changes through GitHub:

1. **Fork and Clone**: Fork the upstream repository at `https://github.com/weaviate/weaviate-io` and clone it locally.
2. **Set Tracking Branches**: Set the remote tracking branch to monitor upstream changes. When creating a new project branch, add `upstream/main` as a tracking branch.
3. **Install Dependencies**: Switch to the project directory and run `yarn` to update and install dependencies.
4. **Run a Local Server**: Start the `yarn` server to build the site and launch a local preview at `http://localhost:3000/`. The server can be stopped by closing the terminal or pressing `Ctrl+C`/`Cmd+C`.
5. **Verify and Submit**: Double-check all links before submitting a merge request. Working links should be removed from the `URL_IGNORES` list, while broken links should be reported directly in the pull request against the `upstream/main` branch.

#Weaviate #Docusaurus #OpenSource #Documentation

---

*Source: [weaviate/weaviate-io](https://github.com/weaviate/weaviate-io)*
