---
title: "OpenHands Cloud Introduces Scheduled and Event-Driven Automation Execution Service"
slug: "openhands-cloud-introduces-scheduled-and-event-driven-automation-execution-service"
description: "A new automation execution service has been developed for OpenHands Cloud, providing support for both scheduled and event-driven automation workflows."
date: 2026-11-09T06:07:25+05:30
tags: [OpenHands, Automation, Python, FastAPI, DevOps]
categories: ["AI", "AI Agents", "Cloud Infrastructure", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/225919603?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenHands Cloud Introduces Scheduled and Event-Driven Automation Execution Service

A new automation execution service has been developed for OpenHands Cloud, providing support for both scheduled and event-driven automation workflows.

## 🔍 Overview

The Automation Service allows users to manage and execute agent workflows based on predefined schedules or external triggers. Key features include:

* **Scheduled Automations:** Run OpenHands conversations on a cron schedule.
* **Event-Driven Automations:** Trigger automations via webhooks, such as GitHub events.
* **API Key Management:** Per-user API keys for secure automation access.
* **Run History:** Track automation runs with status and results.

## 🧩 How it works

System responsibilities are divided across several components:

* **Automation Service:** Owns automation definitions, cron scheduling, webhooks, run history, dispatch, and sandbox lifecycle orchestration.
* **Agent Server and OpenHands/software-agent-sdk:** Execute agent conversations and own agent/tool behavior, workspaces, events, and API endpoints.
* **OpenHands/typescript-client:** Provides typed browser access to the Agent Server API.
* **OpenHands/OpenHands:** Owns the Agent Canvas UI and frontend integration.

The codebase is structured into specific modules:

| File | Description |
| --- | --- |
| `app.py` | FastAPI application entry point |
| `router.py` | API routes for CRUD operations |
| `scheduler.py` | Background scheduler for cron jobs |
| `dispatcher.py` | Dispatches pending runs to OpenHands |
| `models.py` | SQLAlchemy models |
| `schemas.py` | Pydantic schemas for API |

## ⚙️ Key details

The service is built using Python 3.12+ and uses `uv` for dependency management. For storage, it utilizes PostgreSQL, with `testcontainers` available for testing.

Database migration and creation rules include:

* SQLite databases are migrated on startup.
* PostgreSQL databases are not migrated on startup unless `AUTOMATION_RUN_MIGRATIONS_ON_STARTUP=true` (or `1`) is set. When set, each replica runs `alembic upgrade head` before serving requests, using an advisory lock so concurrent replicas take turns. A failed migration stops the replica from starting.
* Setting `AUTOMATION_CREATE_DATABASE_IF_MISSING=true` (or `1`) instructs migrations to connect to the `postgres` database and create the target database if missing. This requires the database user to have the `CREATEDB` privilege.

## 🚀 Deployment

For local development, dependencies can be installed using `uv sync --group dev`, and the application can be run with `uv run uvicorn openhands.automation.app:app --host 0.0.0.0 --port 8000 --reload`.

Container deployment can be built and run using Docker:

* `docker build -t automation -f containers/Dockerfile .`
* `docker run -p 8000:8000 automation`

The service is deployed via the deploy repository at `https://github.com/All-Hands-AI/deploy`. Docker images are automatically built and pushed to `ghcr.io/openhands/automation` on every push to main and on tags.

#OpenHands #Automation #Python #FastAPI #DevOps

---

*Source: [OpenHands/automation](https://github.com/OpenHands/automation)*
