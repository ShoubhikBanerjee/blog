---
title: "Floci Released as an Open-Source Local AWS Emulator"
slug: "floci-released-as-an-open-source-local-aws-emulator"
description: "Floci is a free, open-source local AWS emulator designed for development, testing, and CI. It provides AWS-shaped services on a local machine without requiring a cloud account, paid feature gates, or..."
date: 2026-09-17T12:07:20+05:30
tags: [AWS, OpenSource, Emulator, CloudDevelopment, CI]
categories: ["AI", "Cloud Computing", "Software Development", "DevOps Tools"]
image: "https://avatars.githubusercontent.com/u/271436837?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Floci Released as an Open-Source Local AWS Emulator

Floci is a free, open-source local AWS emulator designed for development, testing, and CI. It provides AWS-shaped services on a local machine without requiring a cloud account, paid feature gates, or an auth token.

## 🔍 Overview

Floci acts as a drop-in replacement that allows users to maintain existing workflows by pointing tools to `http://localhost:4566`. Supported tools include:

* AWS SDK
* AWS CLI
* Terraform
* CDK
* OpenTofu
* Test suites

## ⚙️ Key details

Floci is part of a broader emulator family providing local environments for various cloud providers:

| Emulator | Cloud Provider | Port |
| :--- | :--- | :--- |
| floci | AWS | 4566 |
| floci-az | Azure | 4577 |
| floci-gcp | GCP | 4588 |
| floci-oci | OCI | 4599 |

Technical specifications for the AWS emulator include:
* **Image:** `floci/floci:latest`
* **Ports:** `4566:4566`
* **Regions:** Any region works.
* **Credentials:** Any non-empty values are accepted unless stricter service-specific auth checks are explicitly enabled.
* **Deployment:** The official CLI is the fastest way to run Floci.

## 🧩 How it works

Floci includes a browser console for inspecting local emulator resources, accessible at `http://localhost:4566/_floci/ui`. The console operates as follows:

* The first request pulls the console image (`floci/floci-ui:latest`) and starts it as a sidecar container on Floci's Docker network.
* Logs are streamed into CloudWatch Logs under `/floci/ui`.
* Starting a container requires the Docker socket (`/var/run/docker.sock:/var/run/docker.sock`).

Configuration options for the UI include:

* `FLOCI_SERVICES_UI_ENABLED`: Enable the console sidecar (default: true).
* `FLOCI_SERVICES_UI_IMAGE`: Console image to run (default: `floci/floci-ui:latest`).
* `FLOCI_SERVICES_UI_CONTAINER_NAME`: Name of the sidecar container (default: `floci-ui`).
* `FLOCI_SERVICES_UI_PORT`: Host port the console is published on (default: 4500).
* `FLOCI_SERVICES_UI_KEEP_RUNNING_ON_SHUTDOWN`: Leave the sidecar running when Floci stops (default: false).

Note: The old `hectorvent/floci` repository no longer receives updates.

#AWS #OpenSource #Emulator #CloudDevelopment #CI

---

*Source: [floci-io/floci](https://github.com/floci-io/floci)*
