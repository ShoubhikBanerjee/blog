---
title: "IBM Time-Series Foundation Models Now Run Natively on Confluent"
slug: "ibm-time-series-foundation-models-now-run-natively-on-confluent"
description: "IBM and Confluent have made time-series foundation models available natively on Confluent, enabling real-time forecasting, anomaly detection, and optimization for streaming data. These models, which..."
date: 2026-11-18T22:09:17+05:30
tags: [TimeSeries, IBM, Confluent, StreamProcessing, ApacheFlink]
categories: ["AI", "Machine Learning", "Data Engineering", "Time Series Analysis"]
image: "https://cdn-uploads.huggingface.co/production/uploads/64e8143f6de557454220921e/yf6E9vJHIkGHG_toGSasb.gif"
author: "Shoubhik Banerjee"
draft: false
---

# IBM Time-Series Foundation Models Now Run Natively on Confluent

IBM and Confluent have made time-series foundation models available natively on Confluent, enabling real-time forecasting, anomaly detection, and optimization for streaming data. These models, which have accumulated more than 50 million downloads, now run on CPUs in both cloud and on-premises environments.

## 🧩 How it works
Every business generates a continuous record of change, such as machine readings, payments, or inventory changes. These observations form time series that carry signals for anticipating future events. A forecast delivered after an event is too late to influence the outcome, so IBM and Confluent are bringing these models closer to the data as it flows.

*   **Streaming Integration:** Using Apache Flink, teams can apply forecasting, anomaly detection, and semantic intelligence to streaming data using SQL.
*   **Model Capabilities:** Time-series foundation models learn general patterns from diverse historical data and apply that knowledge to new series and tasks. This provides a starting point without requiring teams to train a separate model for every series.
*   **Flexibility:** Depending on the task, teams can fine-tune a model or combine its outputs with other data and business logic.
*   **Architecture:** Confluent’s Data Streaming Platform brings together connect, stream, process, govern, and query capabilities. Apache Flink transforms and enriches data as it flows, while Lightning Tables provide low-latency access to the current state. Time-series models add predictive power to this architecture by preparing data, invoking forecasts, and making results available alongside the events that produced them.

## ⚙️ Key details
The time-series foundation models run natively inside Confluent as built-in functions.

*   **Deployment:** In Confluent Cloud, the service is fully managed with nothing to deploy. On premises, the models run within your own infrastructure using Confluent Platform for Apache Flink.
*   **Hardware:** The models run on standard CPUs, without requiring GPUs. This reduces the need for dedicated GPU infrastructure and simplifies deployment.
*   **Data Input:** Forecasts can incorporate recent observations as part of a streaming workflow, subject to the model’s requirements and the pipeline’s configuration.

## 💡 Why it matters
These building blocks can be applied across manufacturing, retail, banking, and airlines, bringing insights closer to where decisions are made. They support mission-critical use cases such as keeping production lines in spec, detecting unusual store activity, improving product-level planning, assessing card payments, and forecasting trading volume.

*   **Manufacturing Example:** An ice cream line’s quality depends on "overrun"—the amount of air whipped into the mix. A pretrained model reads SCADA telemetry and QA measurements every 10 minutes. It forecasts the share of tubs expected to be in spec four hours ahead, along with a likely range.
*   **Operational Impact:** Forecasts and anomalies can be routed to operational applications sooner, allowing teams to combine them with business context, rules, and human judgment.

#TimeSeries #IBM #Confluent #StreamProcessing #ApacheFlink

---

*Source: [Time-Series Models in the Streamhouse: A New Frontier and Use Cases](https://huggingface.co/blog/ibm-research/time-series-powered-streamhouse)*
