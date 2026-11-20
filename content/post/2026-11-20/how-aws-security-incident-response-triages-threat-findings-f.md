---
title: "How AWS Security Incident Response triages threat findings from GuardDuty"
slug: "how-aws-security-incident-response-triages-threat-findings-from-guardduty"
description: "AWS Security Incident Response continuously triages threat findings from Amazon GuardDuty and AWS Security Hub CSPM, a process where most work never surfaces as a customer-facing case. The service..."
date: 2026-11-20T22:08:48+05:30
tags: [AWS, Security, GuardDuty, IncidentResponse, ThreatDetection]
categories: ["AI", "Cloud Security", "Incident Response", "Threat Intelligence", "AWS Services"]
image: "https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/18/automated-triage-hero-1260x630.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# How AWS Security Incident Response triages threat findings from GuardDuty

AWS Security Incident Response continuously triages threat findings from Amazon GuardDuty and AWS Security Hub CSPM, a process where most work never surfaces as a customer-facing case. The service ingests these findings through Amazon EventBridge rules automatically deployed during onboarding, ensuring that active threats are evaluated while posture and compliance issues remain in existing remediation processes.

## 🧩 How it works

The automated triage process evaluates each finding payload against several data sources to determine if an activity is benign or requires action. 

- **Data sources:** The service assesses the finding payload, related AWS activity from AWS CloudTrail and Amazon VPC Flow Logs, AWS threat intelligence, and user-provided environment context.
- **Benchmarking:** Findings are mapped against a profile of known-good activity specific to the customer's environment.
- **Third-party integration:** Findings from tools like CrowdStrike, Trend Micro, or Lacework sent to Security Hub CSPM are also ingested, provided they carry complete payload information including resource ID, account ID, timestamp, and threat details. GuardDuty findings are ingested directly to prevent duplication.

## ⚙️ Key details

Outcomes of the triage process vary depending on the nature of the finding. Posture and compliance findings, such as misconfigurations or failed benchmark checks, are not triaged as they reflect environment state rather than active threats. They remain current without archiving and do not generate cases.

For active threat findings, such as compromised credentials, cryptomining, or data exfiltration, the service determines one of three dispositions:

| Disposition | Trigger Condition | Action Taken |
|---|---|---|
| Archived, no action needed | Automated triage or engineer confirms activity is benign or expected | Finding is archived in GuardDuty; no case is created and no customer contact is made |
| Proactive case opened | Triage cannot confirm activity is benign | Case is opened as "Unconfirmed Activity" or "Inappropriate/Unintended Activity"; incident response team is engaged; finding stays Current until resolved |
| Retained for review | Posture-related findings (e.g., overly permissive policies) | No case is created; finding remains Current without archiving |

When a proactive case is opened, customers respond via the AWS Management Console under the Cases section, allowing direct communication, context sharing, and case resolution. For third-party findings ingested through Security Hub CSPM, the disposition logic mirrors GuardDuty, but the status changes from NEW to NOTIFIED when triage begins, moving to SUPPRESSED if cleared as benign.

## 💡 Why it matters

The service builds a profile of what is normal in your environment to distinguish between expected behavior and genuine threats. For example, if GuardDuty flags an "UnauthorizedAccess:IAMUser/InstanceCredentialExfiltration.OutsideAWS" finding, the service checks if the external IP belongs to a known corporate VPN range. If the pattern is recognized, the finding is archived. If the IP is from a hosting provider with no prior association and the IAM role has never called from outside AWS, a proactive case is created for investigation. Across customers, less than 1 percent of ingested findings result in a customer-facing escalation.

![AWS Security Incident Response Triage](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/18/aws-security-incident-response-triage-b-hybrid-Figure-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2026/11/18/aws-security-incident-response-triage-b-hybrid-Figure-1.png)

#AWS #Security #GuardDuty #IncidentResponse #ThreatDetection

---

*Source: [How AWS Security Incident Response triages your security findings | Amazon Web Services](https://aws.amazon.com/blogs/security/how-aws-security-incident-response-triages-your-security-findings/)*
