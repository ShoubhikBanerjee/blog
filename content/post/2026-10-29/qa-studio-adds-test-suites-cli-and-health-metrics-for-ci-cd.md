---
title: "QA Studio adds test suites, CLI and health metrics for CI/CD"
slug: "qa-studio-adds-test-suites-cli-and-health-metrics-for-ci-cd"
description: "We announced an update to QA Studio – the reference solution built with Amazon Nova Act – that expands the platform with batch regression testing, a command‑line interface, and richer..."
date: 2026-10-29T18:01:40+05:30
tags: [AmazonNovaAct, QAStudio, CICD, Testing]
categories: ["AI", "Software Testing", "AI Operations", "DevOps", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-21434-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# QA Studio adds test suites, CLI and health metrics for CI/CD

## 🔍 Overview
We announced an update to QA Studio – the reference solution built with Amazon Nova Act – that expands the platform with batch regression testing, a command‑line interface, and richer health‑monitoring dashboards.

## 🧩 How it works
- **Applications** represent the system under test (a website, web app, or service front end).  Creating an application requires a name, a base URL, and an optional set of environments such as development, staging, and production.
- **Use cases** are the individual natural‑language tests defined in Part 1.  They belong to an application and inherit its ownership.
- **Test suites** are collections of use cases for regression testing (added in this update).  They also belong to an application.
- Tests are executed through AI‑powered visual navigation that records every run as Amazon CloudWatch custom metrics, dimensioned by application and environment.

## ⚙️ New capabilities (Update)
- **Batch regression testing** via test suites can be run from a new CLI, making it easy to integrate into continuous integration and continuous delivery (CI/CD) pipelines.
- **Health dashboard** shows three top‑level figures for a selected window: pass rate, total executions, and current failure count.
- A **health score** (0–100) is computed from the pass rate with a penalty for flaky tests.
- Teams can select a 7‑day window with hourly granularity or a 30‑day window with daily granularity; the UI charts executions, successes, failures, and average duration.
- Because metrics carry an environment dimension, views can be filtered to a single environment, allowing comparisons such as staging vs. production for the same tests.
- **Flaky tests view** ranks use cases by how often they flipped between passing and failing over the last seven days.
- **Recent failures view** lists the latest failed executions for quick triage, each linking to the Amazon Nova Act trajectory logs and session recordings.

## 👥 Access control
QA Studio organizes access around teams. An application belongs to exactly one team, and every team member holds one of five cumulative roles:

| Role | What the role can do |
|------|----------------------|
| Administrator | Studio‑wide access to every team, application, and user; can create teams and assign applications |
| Team Lead | Manages their own team members and creates applications for the team |
| Editor | Creates and edits use cases and test suites within the team’s applications |
| Viewer | (lowest role; inherits permissions of roles below it) |

Access to a use case or test suite follows the application that contains it – if a member can work with the application, they can work with its tests, bounded by their role.

The **Users** page lists every account with its team and role. In the reference deployment, four users span two teams: two Team Leads, one Viewer, and one Studio‑wide Administrator.

## 📊 Observability details
- Every execution is recorded as a CloudWatch custom metric.
- The dashboard presents pass rate, execution count, failure count, and a health score.
- Charts can be filtered by environment, enabling side‑by‑side comparison of staging and production results.
- Flaky‑test rankings and recent‑failure listings help teams triage unstable or broken tests quickly.

## 🚀 Availability
The new CLI, test suite management, and health‑metric views are now part of the QA Studio reference deployment and can be used in CI/CD pipelines.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-21434-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-21434-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-21434-3-1.png)

#AmazonNovaAct #QAStudio #CICD #Testing

---

*Source: [Accelerating software delivery with agentic QA automation using Amazon Nova Act – Part 3 | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/accelerating-software-delivery-with-agentic-qa-automation-using-amazon-nova-act-part-3/)*
