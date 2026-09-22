---
title: "Tata Elxsi Launches IRIS Industrial Safety Platform on AWS"
slug: "tata-elxsi-launches-iris-industrial-safety-platform-on-aws"
description: "Tata Elxsi has developed IRIS, a real-time industrial vision platform built on AWS to help organizations convert existing camera infrastructure into actionable intelligence for industrial safety."
date: 2026-09-22T22:03:42+05:30
tags: [TataElxsi, AWS, IndustrialSafety, ComputerVision, EdgeComputing]
categories: ["AI", "Computer Vision", "Industrial IoT", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/18/ML-19998-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Tata Elxsi Launches IRIS Industrial Safety Platform on AWS

Tata Elxsi has developed IRIS, a real-time industrial vision platform built on AWS to help organizations convert existing camera infrastructure into actionable intelligence for industrial safety.

## 🔍 Overview
IRIS is designed for organizations that operate camera infrastructure but cannot currently turn those feeds into real-time intelligence. The platform addresses a gap where the detection of unsafe conditions typically takes 15–45 minutes, depending on operator availability.

## 🧩 How it works
Tata Elxsi built IRIS as a serverless, event-driven pipeline that follows a specific repeatable pattern:

* **Observe:** Data is captured at the edge.
* **Detect:** Computer vision is used for detection.
* **Analyze:** Context is analyzed.
* **Alert:** Notifications are sent to the appropriate personnel.
* **Store:** Data is saved for compliance.
* **Learn:** The system learns from production data.

## ⚙️ Key details

| Component | Specification/Function |
| :--- | :--- |
| **AWS Region** | Asia Pacific (Mumbai) for data-residency and low-latency proximity to Indian facilities |
| **Edge Compute Tier** | AWS IoT Greengrass on GPU-equipped servers (e.g., NVIDIA Jetson AGX Orin) |
| **Connectivity** | Connected to camera networks over RTSP/ONVIF |
| **Edge Processing** | Extracts 2-5 frames per second with motion-based filtering and a first-pass model for people, vehicles, or equipment |
| **Cloud Storage** | Amazon S3 buckets partitioned by camera, date, and hour |
| **Event Backbone** | Amazon Kinesis Data Streams in on-demand capacity mode |

### Technical Efficiency
* **Data Reduction:** Filtering at the edge reduces the volume of frames sent to the cloud by roughly 70–80 percent based on customer production measurements.
* **Payload Optimization:** The pipeline streams structured event data rather than continuous video. Events are kept under 1 KB, carrying the Amazon S3 object key and context such as camera ID, plant, zone, and an NTP-synchronized timestamp.
* **Cloud Integration:** AWS IoT Greengrass is used to manage secure device communication and deliver updated models from Amazon S3 as Greengrass components.

#TataElxsi #AWS #IndustrialSafety #ComputerVision #EdgeComputing

---

*Source: [How Tata Elxsi detects industrial safety risks in seconds on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-tata-elxsi-detects-industrial-safety-risks-in-seconds-on-aws/)*
