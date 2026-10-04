# S-OS Deployment Plan — plain-language README

## What this is
A single planning document describing how the S-OS command hub could be hosted at large scale in the cloud. It is a written plan, not working code.

## Who it's for
Whoever eventually sets up big, production-grade hosting for S-OS, and anyone estimating what that would cost.

## What it does today
The document (the file named `sos-deployment`) covers:
- **Where to host:**
  - Microsoft Azure as the main home
  - Amazon AWS as a backup in case Azure goes down
  - Google Cloud for AI work that needs graphics cards
  - an own-servers option
- **How the pieces are arranged** using Kubernetes, a system that runs and restarts many programs automatically. The pieces include:
  - a database (PostgreSQL)
  - a cache (Redis)
  - a message queue (RabbitMQ)
  - a search store for AI (Qdrant)
- **Traffic and security:** a front door for incoming requests, login checks, limits on how often each user can call, and rules on who can access what.
- **Automatic publishing steps** on GitHub, including how to undo a bad release.
- **Setup-as-code** (Helm and Terraform), so the cloud resources can be created from files instead of by hand.
- **Monitoring** with Prometheus and Grafana (graphs and alerts).
- **A monthly cost estimate.**

## How to run it
Nothing to run. Read the `sos-deployment` file.

## Current status and known gaps
- Plan only. None of the files it describes are in this repo:
  - Kubernetes files
  - Helm chart
  - Terraform
  - workflows
  - scripts
- The S-OS repo itself currently uses a much simpler setup (n8n + Supabase + Docker).

## Where things live
| File | What's in it |
|---|---|
| `sos-deployment` | The full plan |
