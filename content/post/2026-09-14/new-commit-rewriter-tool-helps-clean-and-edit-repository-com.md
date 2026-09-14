---
title: "New commit-rewriter Tool Helps Clean and Edit Repository Commit Messages"
slug: "new-commit-rewriter-tool-helps-clean-and-edit-repository-commit-messages"
description: "A new web application tool called `commit-rewriter` has been created to assist developers in editing repository commit messages. The tool was developed to clean up commits that are unfit for public..."
date: 2026-09-14T18:04:24+05:30
tags: [Git, DeveloperTools, OpenSource]
categories: ["AI", "Developer Tools", "Software Development", "Open Source"]
image: "https://static.simonwillison/static/2026/commit-rewriter.webp"
author: "Shoubhik Banerjee"
draft: false
---

# New commit-rewriter Tool Helps Clean and Edit Repository Commit Messages

A new web application tool called `commit-rewriter` has been created to assist developers in editing repository commit messages. The tool was developed to clean up commits that are unfit for public release.

## 🔍 Overview
The tool was initially built to edit commit messages for Datasette security releases. The original commits contained coding agent cruft and references to private repository issue IDs, which made them unsuitable for publication.

## ⚙️ Key details
To edit the commit messages for a repository, you can run the tool with the following command:

```bash
uvx commit-rewriter path/to/repo
```

If you are already inside the directory of the target repository, you can omit the path from the command.

## 🧩 How it works
* **Safety Reverts**: When you submit your edits, the tool automatically creates a timestamped branch of your current repository state, allowing you to revert if needed.
* **Sequential Rewriting**: The tool rewrites every commit from the first commit you edited to the most recent one.

![figure](https://static.simonwillison.net/static/2026/commit-rewriter.webp)

#Git #DeveloperTools #OpenSource

---

*Source: [Release: commit-rewriter 0.1](https://simonwillison.net/2026/Sep/14/commit-rewriter/)*
