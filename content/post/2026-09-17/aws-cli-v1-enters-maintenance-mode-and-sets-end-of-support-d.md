---
title: "AWS CLI v1 Enters Maintenance Mode and Sets End-of-Support Date"
slug: "aws-cli-v1-enters-maintenance-mode-and-sets-end-of-support-date"
description: "The AWS CLI v1, which provides a unified command line interface to Amazon Web Services, has entered maintenance mode as of August 5, 2026."
date: 2026-09-17T22:02:13+05:30
tags: [AWS, AWSCLI, CloudComputing, DeveloperTools]
categories: ["AI", "Cloud Infrastructure", "Software Development", "Technical Updates"]
image: "https://avatars.githubusercontent.com/u/2232217?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AWS CLI v1 Enters Maintenance Mode and Sets End-of-Support Date

The AWS CLI v1, which provides a unified command line interface to Amazon Web Services, has entered maintenance mode as of August 5, 2026.

## ⚙️ Key details

* **Maintenance Mode:** Starting August 5, 2026, releases are limited to security issues and critical bug fixes only.
* **End-of-Support:** The AWS CLI v1 will reach end-of-support on July 15, 2027.
* **Limitations:** The version will not receive updates for existing or new services, nor will it be updated to support new regions.

## 🧩 How it works

### Installation and Requirements
Installation uses packaging features from setuptools (recommended 36.2.0 or greater) and pip (recommended 9.0.2 or greater). 

* **Supported Python Versions:** 3.10.x, 3.11.x, 3.12.x, 3.13.x, and 3.14.x (and greater).
* **Installation Methods:**
    * Virtualenv using pip (the safest way).
    * Bundled installer for Mac OS and Linux.
    * MSI Installer for Windows.

### Configuration
Users must configure AWS credentials before use via the following methods:

| Method | Detail |
| :--- | :--- |
| Configuration command | Run the `aws configure` command for the quickest start |
| Environment variables | Use `export AWS_ACCESS_KEY_ID` and `export AWS_SECRET_ACCESS_KEY` |
| Shared credentials file | Create an INI file in `~/.aws/credentials` (or `%UserProfile%\.aws\credentials` on Windows) |
| Config file | Create an INI formatted file |
| IAM Role | Available configuration method |

If the shared credentials file is placed in a custom location, the `AWS_SHARED_CREDENTIALS_FILE` environment variable must be set.

#AWS #AWSCLI #CloudComputing #DeveloperTools

---

*Source: [aws/aws-cli](https://github.com/aws/aws-cli)*
