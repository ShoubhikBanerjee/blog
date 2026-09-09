---
title: "Automating Custom Permissions Assignment in Quick"
slug: "automating-custom-permissions-assignment-in-quick"
description: "Quick has introduced architectural patterns to automate the assignment of custom permissions, allowing organizations to enforce fine-grained access control across the user lifecycle."
date: 2026-09-09T22:05:26+05:30
tags: [Quick, AWS, AccessControl, Automation, IAM]
categories: ["AI", "Cloud Security", "Data Management", "Software Architecture"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/02/ML-21102-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Automating Custom Permissions Assignment in Quick

Quick has introduced architectural patterns to automate the assignment of custom permissions, allowing organizations to enforce fine-grained access control across the user lifecycle.

## 🔍 Overview

Custom permissions enable administrators to toggle specific features on or off for individual users. This allows for precise control, such as enabling financial analysts to author reports without exporting raw data, or allowing external partners to view dashboards without accessing sharing controls. 

Permissions follow a three-level hierarchy where settings are applied as follows:
* **User-level**: Overrides role-level settings.
* **Role-level**: Overrides account-level settings.
* **Account-level**: The base level of the hierarchy.

## 🧩 How it works

Organizations can use four architectural patterns to automate permissions based on their specific needs:

| Method | Application Scenario |
| :--- | :--- |
| `RegisterUser` API | Applies permissions during user creation via the `--custom-permissions-name` parameter; common for SaaS companies restricting features like GenBI and paginated reports based on pricing tiers. |
| `UpdateAccountCustomPermission` API | Sets a fallback profile for any user without an explicit assignment, including those created via Just-In-Time provisioning. |
| `UpdateRoleCustomPermission` API | Sets a default custom permission profile per Quick role (READER, AUTHOR, ADMIN, and PRO roles). |
| Event-Driven Automation | Uses Amazon EventBridge and AWS Lambda to detect new group memberships (native Quick groups or AWS IAM Identity Center groups) and apply permissions dynamically. |

## ⚙️ Key details

* **Conditional Logic**: For requirements beyond native defaults—such as applying different profiles based on group membership—event-driven automation is used. This is necessary because there is no native API for assigning custom permissions directly to a Group.
* **Complementary Strategies**: Role and account-level defaults (Scenario 2) and group-based automation (Scenario 3) are complementary rather than alternatives. 
* **Provisioning Gaps**: Because Just-In-Time federation creates a window between account creation and group assignment, Scenario 3 only triggers upon the group membership event.
* **Enterprise Scale**: Account-level defaults allow large enterprises to instantly block new features, such as GenBI or connectors, for all users during security reviews without per-user automation.

#Quick #AWS #AccessControl #Automation #IAM

---

*Source: [Automate user-level custom permissions for Amazon Quick | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/automate-user-level-custom-permissions-for-amazon-quick/)*
