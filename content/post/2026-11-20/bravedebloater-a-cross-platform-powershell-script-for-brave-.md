---
title: "BraveDebloater: A Cross-Platform PowerShell Script for Brave Browser Customization"
slug: "bravedebloater-a-cross-platform-powershell-script-for-brave-browser-customization"
description: "BraveDebloater is a new PowerShell-based tool designed to remove specific features and extras from Brave Browser using enterprise policies. The script is not affiliated with or endorsed by Brave..."
date: 2026-11-20T22:08:48+05:30
tags: [BraveBrowser, PowerShell, CrossPlatform, BrowserCustomization, OpenSourceTools]
categories: ["AI", "Browser Customization", "Developer Tools", "Cross-Platform Development", "System Administration"]
image: "https://avatars.githubusercontent.com/u/218491571?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# BraveDebloater: A Cross-Platform PowerShell Script for Brave Browser Customization

BraveDebloater is a new PowerShell-based tool designed to remove specific features and extras from Brave Browser using enterprise policies. The script is not affiliated with or endorsed by Brave Software. It operates on Windows, macOS, and Linux, writing native configuration files for each platform to disable chosen components while maintaining full transparency.

## 🧩 How It Works

The tool is built on PowerShell, which serves as the cross-platform runtime. When executed, it writes configuration files native to the operating system:
*   **Windows:** Registry policies
*   **macOS:** Defaults or plist payloads
*   **Linux:** JSON policy files

The script starts in preview mode, meaning no changes are made until the user explicitly adds the `-Apply` flag. Before an apply run, the tool writes a backup unless the user specifies `-NoBackup` for policy-only changes. This backup can be restored using the `-UndoFromBackup` command.

## ⚙️ Supported Features

Users can select specific features to disable via the command-line interface. The tool supports the following Brave-specific surfaces and telemetry options:

| Feature Area | Example Commands/Policy Names |
| :--- | :--- |
| Rewards | `BraveRewardsDisabled` |
| Wallet | `BraveWalletDisabled` |
| VPN | `BraveVPNDisabled` |
| Leo AI Chat | `BraveAIChatEnabled` |
| News | `BraveNewsDisabled` |
| Talk | `BraveTalkDisabled` |
| Playlist | `BravePlaylistEnabled` |
| Email Aliases | `EmailAliasesEnabled` |
| Telemetry | `BraveP3AEnabled`, `BraveStatsPingEnabled`, `BraveWebDiscoveryEnabled` |
| Chromium Metrics | `metrics_reports_enabled` |

An "Extreme" preset can additionally disable background mode, promotions, Browser Labs, new tab cards, shopping list, QR generator, translate prompts, autofill, and the Google search side panel. Optional profile preference cleanup can hide new tab, sponsored background, and toolbar surfaces by editing per-profile Preferences JSON; this step requires closing Brave before applying. DNS-over-HTTPS mode can also be configured via the `-DnsOverHttps` flag.

## 🛡️ Safety and Limitations

The tool is designed with strict safety boundaries:
*   **No Update Disabling:** It does not disable Brave updates, as update policies are on the blocklist.
*   **Shields Protection:** It does not turn off Brave Shields, add allowlists, or weaken Safe Browsing. An optional `-LockShields` add-on can only enforce stricter Shields defaults.
*   **No Binary Patching:** It does not edit hosts files, remove extensions, patch binaries, or install anything into Brave.
*   **Transparency:** It does not run hidden. All set policies are listed in `brave://policy` with their values. The `-Doctor` flag reports the current state in read-only mode.

## 🚀 Usage

To use BraveDebloater, users pick features and copy the matching command from bravedebloater.tersa.tech. Each command previews first. To write the policy, the user adds `-Apply` and then restarts Brave. To undo changes, users follow the preview and apply commands provided in the Restore section.

#BraveBrowser #PowerShell #CrossPlatform #BrowserCustomization #OpenSourceTools

---

*Source: [osfv/BraveDebloater](https://github.com/osfv/BraveDebloater)*
