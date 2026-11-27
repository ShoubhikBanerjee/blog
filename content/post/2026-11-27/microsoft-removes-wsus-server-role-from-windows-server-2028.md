---
title: "Microsoft removes WSUS server role from Windows Server 2028"
slug: "microsoft-removes-wsus-server-role-from-windows-server-2028"
description: "Microsoft will remove the WSUS server role from Windows Server 2028, the next major release of its server operating system, as it encourages enterprises to transition to cloud-based update management..."
date: 2026-11-27T22:09:22+05:30
tags: [Microsoft, WindowsServer, WSUS, ITSecurity, EnterpriseIT]
categories: ["AI", "Enterprise Systems", "Network Security", "Windows Operating Systems", "Cloud Management"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/27/Windows-Server.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft removes WSUS server role from Windows Server 2028

Microsoft will remove the WSUS server role from Windows Server 2028, the next major release of its server operating system, as it encourages enterprises to transition to cloud-based update management tools.

## 🧩 How it works
WSUS (Windows Server Update Services), introduced in 2005 as Software Update Services (SUS), allows IT administrators to manage and distribute updates for Microsoft products across corporate networks with many Windows devices. It provides centralized control over updates, eliminating the need for each device to download them individually from Microsoft's servers. While Windows Server 2028 removes this role, WSUS remains available and supported in earlier releases, including Windows Server 2025, for the duration of their support lifecycles. Organizations can continue to use WSUS on those releases to manage updates for supported Windows client and Windows Server releases, which includes updates to Windows Server 2028.

## ⚙️ Key details
- **Deprecation Status**: Microsoft officially deprecated WSUS in September 2024 but stated it plans to maintain functionality and continue publishing updates through the channel. The company noted that WSUS remains operational but is no longer investing in new features.
- **Enterprise Impact**: The change affects enterprise environments that rely on WSUS to manage updates but does not impact home users or those using Microsoft Configuration Manager.
- **Security Removals**: Windows Server 2028 also removes VBScript (disabled by default in Internet Explorer 11 on Windows 10) and the legacy Windows Management Instrumentation Command-line (WMIC) utility. These removals are intended to thwart a wide range of malware and attack tactics that abuse them. Additionally, Windows Internet Name Service (WINS) support, which was deprecated with the release of Windows Server 2022 in August 2021, is being removed in this version.
- **Recommended Alternatives**: Businesses are encouraged to adopt cloud-based solutions for keeping endpoints and servers up to date. In a September 2024 statement, Microsoft’s Nir Froimovici recommended that organizations transition to cloud tools, including Windows Autopatch and Microsoft Intune for client update management, and Azure Update Manager for server update management.

## 🏭 Enterprise Scenarios
Microsoft recognizes the need to manage updates in disconnected and highly controlled environments. The company stated that it is invested in supporting these scenarios and will share more information as the work progresses.

## 🚀 Availability
Microsoft announced Windows Server 2028 at the Ignite 2026 conference. Early access is available by registering for the Windows Insider Program for Windows Server or applying to enroll in the Windows Server Technology Adoption Program (TAP).

#Microsoft #WindowsServer #WSUS #ITSecurity #EnterpriseIT

---

*Source: [Microsoft removes WSUS server role in Windows Server 2028](https://www.bleepingcomputer.com/news/microsoft/microsoft-removes-wsus-server-role-in-windows-server-2028/)*
