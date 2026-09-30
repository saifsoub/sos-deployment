# sos-deployment

An end-to-end deployment architecture build pack for the S-OS control plane — a single reference
document covering the target infrastructure and every artifact needed to stand it up.

## What the document specifies

- **Infrastructure** — Azure as primary, with AWS for disaster recovery, GCP for ML/GPU workloads, and an on-prem/Kubernetes option
- **Kubernetes layout** — namespace, secrets, and configmaps; StatefulSets for PostgreSQL, Redis, RabbitMQ, and Qdrant; Deployments, Services, and Ingress for the core services
- **Service mesh** — Istio with an ingress controller, API gateway, OAuth2 auth, and rate limiting
- **Aspire AppHost orchestration** — C# `DistributedApplication` wiring the data layer, core services, and frontend
- **CI/CD** — a GitHub Actions workflow with build, infrastructure deploy, Kubernetes deploy, and rollback stages
- **Helm chart** and **Terraform** for AKS, PostgreSQL, Redis, Service Bus, Storage, Key Vault, DNS, and Front Door
- **Data layer** — PostgreSQL initial schema migration with tables, indexes, functions, and triggers
- **Observability** — Prometheus and Grafana plus a custom metrics exporter
- **Security** — network policies, pod security, and RBAC
- **Cost estimation** — monthly run rate

## Layout

| Path | Purpose |
|---|---|
| `sos-deployment` | The full architecture and build pack document |

## Status

This repository holds a planning document, not a runnable codebase. The manifests, Helm chart,
Terraform, workflows, and scripts it describes are not checked in here.
