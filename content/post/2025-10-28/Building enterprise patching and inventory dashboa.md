---
title: "Building Enterprise Patching and Inventory Dashboards Using Amazon QuickSight"
description: "A comprehensive guide to creating AI-powered infrastructure monitoring dashboards
using Amazon QuickSight, AWS Systems Manager, and natural language queries for real-time
patching compliance and inventory visualization."
date: 2025-10-28T02:05:12.194967+05:30
tags: ["AWS", "Amazon QuickSight", "Systems Manager", "Infrastructure Monitoring", "Patching Compliance", "Dashboard", "AI", "Natural Language Processing", "AWS Glue", "Amazon Athena"]
categories: ["Cloud Computing", "DevOps", "Infrastructure Management"]
image: "https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2025/10/22/qs_Architecture.jpg"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Building Enterprise Patching and Inventory Dashboards Using Amazon QuickSight

![Architecture diagram](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2025/10/22/qs_Architecture.jpg)
*Architecture diagram for the enterprise patching and inventory dashboard solution*

In today's fast-paced IT environment, monitoring and visualizing patching compliance across your
 infrastructure is crucial. This comprehensive guide explores how **Amazon QuickSight**
transforms the traditional manual dashboard creation process through AI-powered natural language
 interactions, enabling you to quickly generate insightful patching compliance and inventory visualizations.

## 💡 Solution Overview

The solution leverages several AWS services to automate the creation of Amazon QuickSight
datasets and utilize natural language queries to visualize data. This innovative approach
reduces what was once a multi-step manual process into a few simple prompts, saving valuable
time while maintaining accuracy and providing real-time insights into your organization's patching status.

### 🏗️ Architecture Component

The solution operates through the following key components:

- **AWS Systems Manager (SSM)** - Executes custom scripts to gather inventory information
- **Amazon S3** - Central storage for inventory and patching data
- **AWS Glue** - Data cataloging and crawling services
- **Amazon Athena** - Query engine for data analysis
- **Amazon QuickSight** - AI-powered visualization and dashboard creation
- **AWS CloudFormation** - Infrastructure-as-code deployment

### ⚙️ Key Features

**Infrastructure Insights Collected:**
- Cloud provider information (AWS, on-premises VMware, etc.)
- Total and free disk space with status monitoring
- Disk space percentage and critical alerts
- EC2-specific metadata including hypervisor types, instance types, and driver versions

**Automated Scheduling:**
- Systems Manager Association: Custom inventory collection every 7 days
- AWS Glue Crawler: Data synchronization every 12 hours
- Both intervals are customizable based on organizational requirements

## 📋 Prerequisites

Before implementing this solution, ensure you have:

- ✅ Systems Manager Managed nodes (EC2 instances or hybrid nodes)
- ✅ Systems Manager Inventory enabled on target accounts
- ✅ Systems Manager patch scan/install operations configured
- ✅ Amazon QuickSight user account with **Admin Pro** or **Author Pro** privileges
- ✅ CloudFormation StackSets permissions
- ✅ AWS Organization ID (if using Organizations)

## 🔧 Implementation Walkthrough

### Step 1: Deploy the CloudFormation Stack

1. **Download the CloudFormation template** from the GitHub repository 2. **Configure deployment parameters:**

| Parameter Category | Key Parameters | Description |
| --- | --- | --- |
| **SSM Configuration** | S3 Bucket Name | Central bucket for resource data sync |
| | Target Type | ALL instances, TAG-based, or specific targeting |
| | Tag Key/Value | For tag-based instance targeting |
| **AWS Accounts** | Organization ID | Root ID (r-xxx) or OU ID (ou-xxx) |
| | Account IDs | Specific accounts (leave empty for all) |
| | Regions | Target AWS regions |
| **Amazon Services** | Athena Database | Database name for resource data sync |
| | QuickSight User | QuickSight username for permissions |

### Step 2: Configure QuickSight Permissions

1. **Navigate to Amazon QuickSight console** 2. **Set user role to Admin Pro:**
   - Choose user icon → Manage QuickSight - Select Manage users → Assign Admin Pro role

3. **Configure AWS resource access:** - Under Permissions → AWS resources
   - Enable Amazon Athena and Amazon S3 access - Select the S3 bucket created by CloudFormation

### Step 3: Initialize Data Collection

1. **Wait for SSM Inventory Association** to complete (runs every 30 minutes) 2. **Manually trigger AWS Glue Crawler:**
   - Navigate to AWS Glue Crawlers console - Select crawler starting with "SSM-GlueCrawler-*"
   - Choose **Run** to execute

## 📊 Creating Visuals with Amazon QuickSight AI

### Operations Dashboard Visuals

The following prompts demonstrate how to create comprehensive operational visualizations:

#### 🌐 Managed Nodes by Provider
```
"Create a pie chart for count of resourceid by provider"
```

#### 📊 System Status Overview
```
"Create a donut chart for count of resourceid by instancestatus"
```

#### 💻 Operating System Distribution
```
"Create a donut chart for count of resourceid by platformname"
```

#### 💾 Disk Space Monitoring
```
"Create a visual for count of resourceid by diskspacestatus"
```

![Operations Dashboard](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2025/10/22/qs_operations-1.png)
*Comprehensive operations dashboard showing system health metrics*

### AWS EC2-Specific Analytics

For detailed EC2 insights, use these specialized prompts:

#### ⚡ AWS Driver Versions
```
"Create a visual for count of resourceid by application version and application name equals AWS PV Drivers"
```

#### 🔌 Network Driver Analysis
```
"Create a visual for count of resourceid by enaversion"
```

#### 💳 License Type Distribution
```
"Create a pie chart for count of resourceid by licensetype"
```

![AWS Dashboard](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2025/10/21/qs_aws_dashboard.png)
*AWS EC2 metrics dashboard with detailed component analysis*

### 🛡️ Compliance Monitorin

The compliance sheet focuses on patch and association compliance:

#### Patch Compliance Overview
```
"create a pie chart for count of resourceid by compliance status for compliancetype equals Patch"
```

#### Critical Missing Patches
```
"create a pivot table with provider, accountid, region, platformname, resourceid, patch title
for compliancetype equals Patch and compliance status equal NON_COMPLIANT and patch status equal Missing"
```

![Compliance Dashboard](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2025/10/06/Inventory_compliance_patches.png)
*Detailed compliance dashboard showing patch status across infrastructure*

## 🎯 Interactive Querying

Amazon QuickSight enables real-time questioning of your data through natural language:

**Example queries:**
- *"List of resourceid by diskspacestatus equal Critical"*
- *"Show me all non-compliant Windows servers"*
- *"Display patch compliance by AWS region"*

## 🧹 Cleanup Process

To remove all resources:

1. **CloudFormation Stack:** - Navigate to AWS CloudFormation console
   - Select stack named *ssm-inventory-patching-dashboard* - Choose **Delete** → **Delete stack**

2. **QuickSight Resources:** - Delete Dashboard, Analyses, and Datasets manually

## 🙌 Credits

*Originally posted at: https://aws.amazon.com/blogs/mt/building-enterprise-patching-and-inventory-dashboards-using-amazon-q-in-amazon-quicksuite/*

## ✅ Final Thoughts

This solution demonstrates how Amazon QuickSight's AI capabilities transform infrastructure
monitoring from a complex, time-intensive process into an intuitive, natural language-driven
experience. By combining AWS Systems Manager's comprehensive data collection with QuickSight's
intelligent visualization engine, organizations can:

- **Accelerate dashboard creation** from hours to minutes
- **Improve compliance visibility** across hybrid environments
- **Enable self-service analytics** for non-technical stakeholders
- **Maintain real-time insights** into infrastructure health

The integration of multiple AWS services creates a robust, scalable solution that grows with
your organization's needs while simplifying the complexity of enterprise infrastructure monitoring.

Transform your infrastructure monitoring today by implementing this AI-powered visualization
solution and experience the future of intelligent operational dashboards.

--- 
*#AWS #CLOUD #SYSTEMSMANAGER #QUICKSIGHT #PATCHING #COMPLIANCE #DASHBOARD #AI #AUTOMATION
#INFRASTRUCTURE*

