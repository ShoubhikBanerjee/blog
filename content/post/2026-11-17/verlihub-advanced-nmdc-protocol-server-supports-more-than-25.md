---
title: "Verlihub Advanced NMDC Protocol Server Supports More Than 25k Users"
slug: "verlihub-advanced-nmdc-protocol-server-supports-more-than-25k-users"
description: "Verlihub is an advanced NMDC+S protocol server for Linux and Windows operating systems. It offers a high-performance solution with low RAM and CPU usage, capable of holding more than 25,000 users."
date: 2026-11-17T22:09:21+05:30
tags: [Verlihub, NMDC, ServerSoftware, OpenSource, Networking]
categories: ["AI", "Server Infrastructure", "Networking", "Open Source Software"]
image: "https://avatars.githubusercontent.com/u/1856420?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Verlihub Advanced NMDC Protocol Server Supports More Than 25k Users

Verlihub is an advanced NMDC+S protocol server for Linux and Windows operating systems. It offers a high-performance solution with low RAM and CPU usage, capable of holding more than 25,000 users.

## 🔍 Overview
Verlihub provides high-level functionality for managing connections, hub administration, and security features. It uses epoll on Linux and Windows, and supports worker threads for slow work to maintain performance efficiency.

## ⚙️ Key details
- **Resource Efficiency**: Low RAM and CPU usage using epoll on both Linux and Windows operating systems.
- **Capacity**: Able to hold more than 25,000 users.
- **Security**: Built-in TLS-encrypted connections using OpenSSL, supporting plain and encrypted users on the same port. An external TLS proxy is also supported, sending the real address of the user with the `$MyIP` command.
- **Database Support**: Offers backup and restore functionality for MySQL or MariaDB databases.
- **Customization and Localization**: Allows extending functionality via Lua scripts (including HTTP requests) and supports hub messages in many languages.
- **User and Connection Management**: Handles user management with privileges, clients and connections management, and logging of user IPs and complete MyINFOs (requires Ledokol).
- **GeoIP Integration**: Tracks the GeoIP country, city, and ASN of users using MaxMindDB.
- **Statistics**: Generates statistics for your hub (requires Ledokol).

## 🚀 Availability
Verlihub builds on Windows with MinGW-w64, with dependencies and build steps detailed in `Install.md`. TLS support is built-in using OpenSSL and enabled by default; to build without it, the `-DUSE_TLS=OFF` flag can be used.

Several resources are available for support and integration:
- Website: https://github.com/verlihub
- Wiki: https://github.com/verlihub/verlihub/wiki
- Crash: https://crash.verlihub.net
- Translate: https://explore.transifex.com/feardc/verlihub
- Ledokol: https://ledo.feardc.net
- MMDB: https://ledo.feardc.net/mmdb
- Support: nmdcs://hub.verlihub.net:7777
- Hublist: https://te-home.net/?do=hublist

#Verlihub #NMDC #ServerSoftware #OpenSource #Networking

---

*Source: [Verlihub/verlihub](https://github.com/Verlihub/verlihub)*
