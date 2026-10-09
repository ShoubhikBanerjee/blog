---
title: "QAD ERP Reporting Extends to Microsoft Fabric via Open Mirroring"
slug: "qad-erp-reporting-extends-to-microsoft-fabric-via-open-mirroring"
description: "Manufacturers using QAD ERP can combine multiple reporting layers, and a new mirroring path now moves QAD data into Microsoft Fabric."
date: 2026-10-09T22:05:01+05:30
tags: [QAD, MicrosoftFabric, PowerBI, DataMirroring]
categories: ["AI", "Enterprise Software", "Business Intelligence", "Data Engineering"]
image: "https://kanerika.com/wp-content/uploads/2025/04/kanerika.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# QAD ERP Reporting Extends to Microsoft Fabric via Open Mirroring

Manufacturers using QAD ERP can combine multiple reporting layers, and a new mirroring path now moves QAD data into Microsoft Fabric.

## 🔍 Overview
- **Layer 1 – Native QAD tools** – Provide operational lookups, formatted documents and financial statements inside the ERP.
- **Layer 2 – Power BI** – Adds interactive analysis; the simplest connection imports QAD data over OpenEdge ODBC on a schedule.
- **Layer 3 – Data warehouse / Microsoft Fabric** – Uses a QAD Fabric mirroring process that runs through Open Mirroring because Microsoft Fabric has no native mirroring source for QAD.

## 🧩 How it works
1. An extraction layer reads tables from the Progress OpenEdge database behind QAD.
2. It writes those tables as Parquet files into a landing zone in OneLake.
3. Microsoft Fabric turns the Parquet files into Delta tables and keeps them current.
4. Each table requires a stable key.

## ⚙️ Key details
- The three layers can be used simultaneously by a manufacturer.
- Power BI connects via OpenEdge ODBC and can be scheduled for regular imports.
- Fabric mirroring relies on Open Mirroring; there is no built‑in source connector for QAD.
- Delta tables in Fabric provide a continuously refreshed view of the ERP data.

## 📊 Layer comparison
| Layer | What it provides | Integration method |
|-------|------------------|--------------------|
| Native QAD tools | Operational lookups, formatted documents, financial statements | Built‑in ERP functionality |
| Power BI | Interactive analysis | OpenEdge ODBC import on a schedule |
| Microsoft Fabric | Mirrored, current Delta tables | Open Mirroring → Parquet → OneLake → Delta |

## 💡 Why it matters
- Combining native ERP reports with Power BI and Fabric gives manufacturers flexible, up‑to‑date analytics.
- The mirroring flow keeps the data warehouse synchronized without a native QAD connector.
- Stable keys ensure reliable table joins and updates within Fabric.

![figure](https://kanerika.com/wp-content/uploads/2026/10/kanerika-qad-erp-reporting-banner-1024x363.webp)

![figure](https://kanerika.com/wp-content/uploads/2026/10/kanerika-qad-fabric-mirroring-banner-1024x363.webp)

#QAD #MicrosoftFabric #PowerBI #DataMirroring

---

*Source: [Kanerika Blog | Latest Articles on AI, ML, Data & Automation](https://kanerika.com/resources/blogs/)*
