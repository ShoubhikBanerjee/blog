---
title: "Spotify outage caused by conflicting deployment changes"
slug: "spotify-outage-caused-by-conflicting-deployment-changes"
description: "On September 29, Spotify experienced an outage that disrupted users’ access to the platform. The disruption was triggered by a series of changes to the deployment platforms that resulted in conflicts..."
date: 2026-11-27T22:09:22+05:30
tags: [Spotify, DevOps, Kubernetes, ArgoCD, IncidentResponse]
categories: ["AI", "DevOps", "Cloud Infrastructure", "Software Engineering"]
image: "https://images.ctfassets.net/p762jor363g1/5Pj1XJpttH7jTwoNtzp0JK/6fe349c743b3f334580c783ee71b7804/tools-orange-c-cream.png"
author: "Shoubhik Banerjee"
draft: false
---

# Spotify outage caused by conflicting deployment changes

On September 29, Spotify experienced an outage that disrupted users’ access to the platform. The disruption was triggered by a series of changes to the deployment platforms that resulted in conflicts impacting the main authentication system, preventing apps from loading content or playing music.

## 🔍 Overview
- The outage began with errors increasing at 13:45 UTC.
- A login system "panic mode alert" paged the owning team at 13:57 UTC.
- Responders identified the specific login service impacted at 14:04 UTC.
- Most regions recovered by 16:30 UTC, though one European region experienced further overwhelm due to returning traffic.
- The incident was declared "all-clear" at 19:34 UTC.

## 🧩 Root Cause Analysis
The issue stemmed from two independently tested changes to the deployment system that conflicted when combined:
- **Change 1**: Altered how test environments are configured, including running fewer instances and omitting some automated health checks.
- **Change 2**: Changed how the system computes the difference between the current state and a desired new state for deployment.

The conflict occurred because one rollout changed the type of deployed workloads (from Kubernetes Deployment to Argo Rollout), while the second changed which configuration parameters are excluded from the automated diff. Consequently, the system accidentally included the `minReplicas` field in the diff. While the correct behavior is for the Kubernetes autoscaler to manage replica numbers, the deployment system instead set the replicas field to the minimum number on every sync.

## ⚙️ Impact and Recovery
- **Token Backlog**: The re-issuing of tokens after downtime caused significant load increases, overwhelming remaining instances even with client backoffs.
- **Reconciliation Loop**: An erroneous reconciliation loop lowered the number of instances, preventing automatic scaling and recovery.
- **Traffic Surge**: The login system handled 200 times more traffic than usual during the start of recovery to process the backlog of missing tokens.
- **Manual Intervention**: The first attempt to manually scale up did not sufficiently account for the traffic increase. By 17:25 UTC, the login system was set to 3x normal CPU/memory resources to prevent a "thundering herd" effect.

## 📊 Incident Timeline
| Time (UTC) | Event |
| :--- | :--- |
| 13:45 | Errors begin increasing |
| 13:57 | Login system "panic mode alert" pages owning team |
| 14:04 | Responders identify the impacted login service |
| 16:30 | Login starts to recover; deployments remain frozen |
| 17:25 | Login set to 3x normal CPU/memory resources |
| 19:34 | Incident declared "all-clear" |

![Spotify Incident Report](https://images.ctfassets.net/p762jor363g1/3AiqgaI6uFPcF6zc7lYX5t/bbed1b145db94423441163d9f149a02e/incident_report.png)

![figure](https://images.ctfassets.net/p762jor363g1/3AiqgaI6uFPcF6zc7lYX5t/bbed1b145db94423441163d9f149a02e/incident_report.png)

#Spotify #DevOps #Kubernetes #ArgoCD #IncidentResponse

---

*Source: [September 29 Outage Incident Report: What we learnt | Spotify Engineering](https://engineering.atspotify.com/2026/11/september-29-outage-incident-report-what-we-learnt/)*
