---
title: "Python 3.15.0 Release Candidate 2 Announced Ahead of October Launch"
description: "Hugo van Kemenade, the release manager for Python 3.14 and 3.15, has announced the release of Python 3.15.0 candidate 2. This version represents the final release candidate phase before the official..."
date: 2026-09-01T22:04:40+05:30
tags: [Python, OpenSource, SoftwareTesting]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Python 3.15.0 Release Candidate 2 Announced Ahead of October Launch

Hugo van Kemenade, the release manager for Python 3.14 and 3.15, has announced the release of Python 3.15.0 candidate 2. This version represents the final release candidate phase before the official launch of Python 3.15.0 scheduled for October.

## 🔍 Overview
With the transition into the release candidate phase, the development process is now restricted. Only reviewed code changes that qualify as clear bug fixes are allowed between this release candidate and the final stable release.

## ⚙️ Key details
*   **Binary Compatibility:** Any binary wheels built against Python 3.15.0 release candidates will work with all future versions of Python 3.15.
*   **Maintainer Action:** Maintainers of third-party projects are strongly encouraged to prepare for the 3.15 release and publish wheels on PyPI now to assist other projects with their testing.
*   **Bug Mitigation:** Testing during the RC period helps prevent shipping bugs in the final release, a lesson learned by developers who have discovered bugs in previous versions, such as Python 3.10, only after they had already shipped.

## 🧩 How it works
While the new RC is not yet available directly for GitHub Actions via `actions/python-versions`, developers can test against it by configuring their testing matrix as follows:

```yaml
strategy:
  matrix:
    python-version: ["3.14", "3.15"]
steps:
  - uses: actions/setup-python@v7
    with:
      python-version: ${{ matrix.python-version }}
      allow-prereleases: true
      check-latest: true
```

The `allow-prereleases` and `check-latest` flags ensure that the workflow automatically tests against the latest candidate (switching from RC1 to RC2 as they land) and eventually the stable version once it is released.

## 🚀 Availability
The final release of Python 3.15.0 is expected in October. Developers and maintainers are encouraged to utilize the current RC2 phase to ensure their projects are ready for the final launch.

#Python #OpenSource #SoftwareTesting

---

*Source: [Python 3.15.0 candidate 2 is here!](https://simonwillison.net/2026/Sep/1/python-315-rc-2/)*
