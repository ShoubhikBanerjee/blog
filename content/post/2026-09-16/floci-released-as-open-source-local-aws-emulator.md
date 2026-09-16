---
title: "Floci Released as Open-Source Local AWS Emulator"
slug: "floci-released-as-open-source-local-aws-emulator"
description: "Floci is a new free, open-source local AWS emulator designed for development, testing, and CI, allowing users to run AWS-shaped services on their own machines."
date: 2026-09-17T00:50:10+05:30
tags: [AWS, OpenSource, CloudComputing, DevOps, Emulator]
categories: ["AI", "Cloud Infrastructure", "Software Development", "DevOps Tools"]
image: "https://avatars.githubusercontent.com/u/271436837?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Floci Released as Open-Source Local AWS Emulator

Floci is a new free, open-source local AWS emulator designed for development, testing, and CI, allowing users to run AWS-shaped services on their own machines.

## 🔍 Overview
Floci serves as a drop-in replacement for AWS services that does not require a cloud account, auth tokens, or paid feature gates. Key capabilities include:

* Compatibility with AWS SDK, CLI, Terraform, CDK, OpenTofu, and test suites.
* Support for any region.
* Acceptance of any non-empty values for credentials, unless stricter service-specific auth checks are explicitly enabled.

## 🧩 How it works
Users can point their workflows to http://localhost:4566 to access all AWS services. The fastest way to run Floci is via the official CLI. For containerized deployments, the following configurations are used:

* **Image:** floci/floci:latest
* **Ports:** 4566:4566
* **Required Volume:** /var/run/docker.sock:/var/run/docker.sock (required to start a container)

## ⚙️ Key details
Floci includes a browser console for inspecting local emulator resources, accessible at http://localhost:4566/_floci/ui. The first request pulls the console image and starts it as a sidecar container on Floci's Docker network, with logs streamed into CloudWatch Logs under /floci/ui.

| Configuration Variable | Default Value | Description |
| :--- | :--- | :--- |
| FLOCI_SERVICES_UI_ENABLED | true | Enable the console sidecar |
| FLOCI_SERVICES_UI_IMAGE | floci/floci-ui:latest | Console image to run |
| FLOCI_SERVICES_UI_CONTAINER_NAME | floci-ui | Name of the sidecar container |
| FLOCI_SERVICES_UI_PORT | 4500 | Host port the console is published on |
| FLOCI_SERVICES_UI_KEEP_RUNNING_ON_SHUTDOWN | false | Leave the sidecar running when Floci stops |

## 🚀 Availability
Floci is the AWS member of a larger emulator family:

| Emulator | Provider | Port |
| :--- | :--- | :--- |
| floci | AWS | 4566 |
| floci-az | Azure | 4577 |
| floci-gcp | GCP | 4588 |
| floci-oci | OCI | 4599 |

Note: The old hectorvent/floci repository no longer receives updates.

#AWS #OpenSource #CloudComputing #DevOps #Emulator

---

*Source: [floci-io/floci](https://github.com/floci-io/floci)*
