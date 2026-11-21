---
title: "Goose database migration tool supports Go functions and out-of-order changes"
slug: "goose-database-migration-tool-supports-go-functions-and-out-of-order-changes"
description: "Goose is a database migration tool available as both a CLI and a library. It allows developers to manage database schemas by creating incremental SQL changes or Go functions."
date: 2026-11-21T18:08:57+05:30
tags: [Goose, Database, Go, CLI, Migrations]
categories: ["AI", "DevOps", "Backend Engineering", "Databases"]
image: "https://avatars.githubusercontent.com/u/18835?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Goose database migration tool supports Go functions and out-of-order changes

Goose is a database migration tool available as both a CLI and a library. It allows developers to manage database schemas by creating incremental SQL changes or Go functions.

## 🔍 Overview
The tool supports migrations for multiple database systems. It works against Postgres, MySQL, MariaDB, Spanner, SQLite, YDB, ClickHouse, MSSQL, and Vertica.

## 🧩 How it works
Goose supports specific migration formats and operational features:
*   Go migrations written as plain functions.
*   Embedded migrations.
*   Out-of-order migrations.
*   Seeding data.
*   Environment variable substitution in SQL migrations.

## ⚙️ Key details
The CLI includes flags for configuring migration behavior. The following table details specific flags and their functions:

| Flag | Description |
| :--- | :--- |
| -allow-missing | Applies missing (out-of-order) migrations |
| -certfile | File path to root CA's certificates in pem format (only supported on MySQL) |
| -dir | Directory with migration files (default ".", can be set via GOOSE_MIGRATION_DIR) |
| -env | Load environment variables from file (default .env) |
| -no-color | Disable color output (NO_COLOR env variable supported) |
| -no-versioning | Apply migration commands with no versioning, in file order |
| -s | Use sequential numbering for new migrations |
| -ssl-cert | File path to SSL certificates in pem format (only supported on MySQL) |
| -ssl-key | File path to SSL key in pem format (only supported on MySQL) |
| -table | Migrations table name (default "goose_db_version") |
| -timeout | Maximum allowed duration for queries to run |

## 🚀 Availability
Goose is available via several installation methods:
*   **Go Install:** `go install github.com/pressly/goose/v3/cmd/goose@latest` installs the binary to your `$GOPATH/bin` directory.
*   **Homebrew:** Available for macOS users.
*   **Docker:** A container image is available for `linux/amd64` and `linux/arm64`.
    *   The container image has no shell and supports `.sql` migrations only.
    *   The working directory is `/migrations`.
    *   Tags include `vX.Y.Z`, `vX.Y`, `vX`, and `latest`.
    *   Dockerfiles can copy the binary using: `COPY --from=ghcr.io/pressly/goose:v3.30.1 /usr/local/bin/goose /usr/local/bin/goose`

#Goose #Database #Go #CLI #Migrations

---

*Source: [pressly/goose](https://github.com/pressly/goose)*
