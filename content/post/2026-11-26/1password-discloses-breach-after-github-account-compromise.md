---
title: "1Password discloses breach after GitHub account compromise"
slug: "1password-discloses-breach-after-github-account-compromise"
description: "1Password disclosed a data breach after an employee's corporate GitHub account was hacked. The attacker used the compromised account to deploy malicious code to the company's backend services to..."
date: 2026-11-26T12:19:42+05:30
tags: [1Password, DataBreach, CyberSecurity, GitHub, Phishing]
categories: ["AI", "Cybersecurity", "Data Privacy", "Software Security"]
image: "https://www.bleepstatic.com/content/hl-images/2023/10/23/1Password_binary.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# 1Password discloses breach after GitHub account compromise

1Password disclosed a data breach after an employee's corporate GitHub account was hacked. The attacker used the compromised account to deploy malicious code to the company's backend services to steal customer data.

## 🔍 Overview

The company began investigating the breach on November 19 after detecting indications that an employee's GitHub account had been compromised. 1Password states that customer password vaults and the encryption keys protecting them were not compromised in the attack.

## 🧩 How it works

The attacker accessed private source code repositories and injected malicious code into backend services that downloaded customer account records. The malicious code also stole internal company source code and accessed the company's continuous integration and continuous delivery (CI/CD) environment, potentially exposing internal infrastructure credentials.

## ⚙️ Key details

The following customer data was stolen in the breach:

- Customer names and email addresses
- Account and user IDs
- Account creation and last sign-in timestamps
- Public cryptographic keys
- Secure Remote Password (SRP) protocol parameters
- Invitation, provisioning, and account recovery tokens
- Other internal account metadata

The stolen tokens were embedded in links that 1Password emailed to users to accept account provisioning invitations or recover their accounts. 1Password says these tokens cannot be used on their own to access customer accounts, as completing the invitation or recovery process requires either single sign-on (SSO) authentication or a six-digit verification code sent to the user's registered email address.

## 🚀 Availability

1Password has disabled the compromised GitHub account, revoked the stolen token, restored clean versions of affected services, and rotated or revoked potentially exposed infrastructure credentials. The company has also hired independent cybersecurity experts to validate its remediation efforts. As a precaution against brute-force attacks, 1Password has strengthened these verification codes from six numeric digits to ten alphanumeric characters. The company states that only a small number of users were affected and have been individually notified.

## 💡 Why it matters

While customer vaults were not compromised, the stolen data is valuable to threat actors as it provides a list of known 1Password users who could be targeted in phishing campaigns. Threat actors could send emails impersonating 1Password, using the breach as a lure to trick customers into disclosing their account passwords, Secret Keys, or recovery verification codes. 1Password is not requiring customers to change their account passwords or Secret Keys but warns them to watch for unexpected invitations, account recovery requests, and other potential phishing attempts.

#1Password #DataBreach #CyberSecurity #GitHub #Phishing

---

*Source: [1Password customer data stolen after employee GitHub account breach](https://www.bleepingcomputer.com/news/security/1password-customer-data-stolen-after-employee-github-account-breach/)*
