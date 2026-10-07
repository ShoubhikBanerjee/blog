---
title: "SOCRadar Alerts Integration Brings External Threat Intel into Elastic Security"
slug: "socradar-alerts-integration-brings-external-threat-intel-into-elastic-security"
description: "Your SOC runs on Elastic. Detections, logs, cases and dashboards all live in Kibana, and your analysts have built their muscle memory around it. Until now, external threat intelligence – alarms about..."
date: 2026-10-07T18:06:06+05:30
tags: [SOCRadar, ElasticSecurity, ThreatIntelligence, SIEM, ECS]
categories: ["AI", "Cybersecurity", "Threat Intelligence", "Security Operations", "Security Analytics"]
image: "https://cdn.socradar.io/wp-content/uploads/2026/10/What-Do-You-Need-to-Know-How-to.png.webp"
author: "Shoubhik Banerjee"
draft: false
---

# SOCRadar Alerts Integration Brings External Threat Intel into Elastic Security

Your SOC runs on Elastic. Detections, logs, cases and dashboards all live in Kibana, and your analysts have built their muscle memory around it. Until now, external threat intelligence – alarms about the Surface, Deep and Dark Web, brand abuse or the external attack surface – arrived in a dedicated platform, were reviewed there, and then manually re‑keyed into the SIEM or case tool. The new SOCRadar Alerts integration (v0.1.0) eliminates that handoff.

## 🔎 Overview
- The integration pulls SOCRadar alarms via the SOCRadar API on a configurable polling interval, with an initial historical look‑back to backfill recent alarms.
- Each alarm arrives with severity, status, alarm type, sub‑type, affected asset, related entities and detailed information.
- Alarm data is mapped to the Elastic Common Schema (ECS), so SOCRadar fields sit next to your other sources with consistent names.

## 🧩 How it works
1. **Polling** – The integration queries the SOCRadar API on the schedule you set.
2. **Normalization** – Incoming alarm fields are translated into ECS fields.
3. **Ingestion** – Normalized alarm documents are stored in the same Elastic workspace used for internal telemetry.
4. **Visualization** – A built‑in Kibana dashboard displays severity distribution, alarm categories, volume trends and recent incidents.
5. **Investigation** – Analysts can pivot from a dashboard tile to the underlying alarm document, correlate it with endpoint or identity events, and open a case without leaving Kibana.

## ⚙️ Key details
- **Alarm attributes** – Every alarm carries:
  - Severity
  - Status
  - Alarm type and sub‑type
  - Affected asset
  - Related entities
  - Detailed description
- **Analyst workflow** – Search, filter and build rules on external alarms exactly as on internal telemetry; prioritize by severity across both.
- **Time saved** – No manual copy‑paste between consoles; the external context that triggered the investigation is already in the case.

| Attribute | What it provides |
|-----------|-----------------|
| Severity | A severity level for prioritization |
| Status | Current processing state of the alarm |
| Alarm type / sub‑type | Classification of the finding |
| Affected asset | The asset the alarm relates to |
| Related entities | Additional objects linked to the alarm |
| Details | Full description and context |

## 🚀 Availability
- The integration is listed in the Elastic integrations catalog. To enable it, open the catalog, search for **SOCRadar**, and add the SOCRadar Alerts integration with your SOCRadar API credentials and polling preferences.
- If you are not yet a SOCRadar customer, or need help configuring the three integrations together, contact your SOCRadar customer success manager or request a demo.

## 💡 Why it matters
- **Unified workspace** – External threat intelligence appears in the same Elastic Security workspace where analysts already work.
- **Reduced handoff** – The costly manual step of re‑keying alarms is removed, eliminating bottlenecks caused by volume and lost context.
- **Actionable context** – Each alarm includes the asset and related entities, so investigations start with concrete, validated information.
- **Continuous visibility** – The built‑in Kibana dashboard gives immediate insight into spikes, such as a high‑severity “New Digital Asset Discovery” followed by an “Impersonating Domain” alarm, enabling rapid response.


![figure](https://cdn.socradar.io/wp-content/uploads/2024/10/Vector.png.webp)

#SOCRadar #ElasticSecurity #ThreatIntelligence #SIEM #ECS

---

*Source: [SOCRadar Alarms in Elastic | Investigate Threats Faster](https://socradar.io/blog/socradar-alarms-in-elastic/)*
