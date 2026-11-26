---
title: "sqlite3_rsync Enables Remote SQLite Database Copies Over SSH"
slug: "sqlite3-rsync-enables-remote-sqlite-database-copies-over-ssh"
description: "sqlite3_rsync is a database remote-copy tool for SQLite that was added as experimental in SQLite 3.47.0 in October 2024 and later enhanced in SQLite 3.50.0 in May 2025. This tool allows copying a..."
date: 2026-11-26T12:19:42+05:30
tags: [SQLite, Database, rsync, SSH, Backup]
categories: ["AI", "Databases", "Software Development", "System Administration"]
author: "Shoubhik Banerjee"
draft: false
---

# sqlite3_rsync Enables Remote SQLite Database Copies Over SSH

sqlite3_rsync is a database remote-copy tool for SQLite that was added as experimental in SQLite 3.47.0 in October 2024 and later enhanced in SQLite 3.50.0 in May 2025. This tool allows copying a snapshot of a SQLite database over an SSH connection without first creating a full local copy, making it useful for systems with limited disk space.

## 🔍 Overview

Normally, grabbing a snapshot copy of a SQLite database requires either the backup API or VACUUM INTO, both of which need enough disk space for a duplicate copy. If you're on a small instance using more than half the available disk, these methods fail. sqlite3_rsync avoids this limitation by transferring data directly over SSH.

It also supports synchronizing an existing database replica without re-transmitting the entire content, reducing network usage.

## 🧩 How it works

The protocol relies on cryptographic hashes:

- The replica sends hashes for pages or groups of pages to the origin.
- The origin responds with differing page content or requests finer-grained hashes if needed.
- If the databases differ significantly, network bandwidth may temporarily exceed the database size due to hash exchange overhead — typically only a few percent more.

## ⚙️ Key details

- Added as experimental in SQLite 3.47.0 (October 2024)
- Enhanced in SQLite 3.50.0 (May 2025)
- Works over SSH
- Avoids local copy requirement
- Efficient for resynchronization

## 🚀 Availability

Available in:

| Version | Date | Status |
|---------|------|--------|
| SQLite 3.47.0 | October 2024 | Experimental |
| SQLite 3.50.0 | May 2025 | Enhanced |

## 💡 Why it matters

For developers working with constrained environments, sqlite3_rsync offers a practical way to back up or sync SQLite databases without exhausting local storage or bandwidth unnecessarily. While initial hash exchanges can add minor overhead, the benefits become clear when managing large or frequently updated databases remotely.

#SQLite #Database #rsync #SSH #Backup

---

*Source: [sqlite3_rsync: Database Remote-Copy Tool For SQLite](https://simonwillison.net/2026/Nov/26/sqlite3-rsync/)*
