---
title: MCP Standards and Enterprise Allowlist
layout: default
---

# MCP Standards and Enterprise Allowlist

Scope: Enterprise adoption of Model Context Protocol (MCP) as the integration layer for agents with SDLC systems. This document specifies standards, security controls, and the allowlist process. Populate citations with first‑party sources in the Appendix.

Last updated: YYYY-MM-DD

## Objectives

- Provide a consistent, auditable interface between agents (IDE/CLI/personal) and SDLC systems.
- Enforce least-privilege access, data minimization, and policy controls.
- Enable vendor diversity while preserving common governance and observability.

## Architecture

- Agents (IDE/CLI/BYOK) connect to an enterprise MCP broker (managed by platform).
- Broker mediates access to curated MCP servers (code search, Jira, CI/CD, KB, etc.).
- All requests pass through a policy gateway (prompt firewall, PII redaction, egress controls).
- Telemetry for every tool invocation is written to SIEM/data lake.

High-level flow:
1) Agent → MCP Broker → Allowlisted MCP Server
2) Broker ↔ Policy Gateway (prompt filters, redaction, allowlists)
3) Broker → Telemetry sink (logs, metrics, traces)

## Security and Policy Controls

- Identity/Access
  - SSO/SCIM-backed identity; per-user tokens; short-lived creds; RBAC on MCP servers.
- Network
  - Private endpoints/VPC; no direct public calls from dev endpoints to LLMs or SDLC systems.
- Data Protection
  - PII/secret redaction; code indexing with encryption at rest; repo scope boundaries.
- Governance
  - Signed MCP integrations; version pinning; provenance tracked; change control on allowlist.
- Observability
  - Structured logs for agent actions and tool calls; correlation IDs across requests; retention per policy.
- Safe Execution
  - Tool invocation allowlist/denylist; dry‑run modes for codemods; rate limits and kill switches.

## Curated MCP Servers (Initial)

- Code search (e.g., Sourcegraph/Zoekt)
- Issue management (Jira/Azure Boards)
- CI/CD (GitHub Actions/Jenkins)
- Secrets scanning, SAST/SCA metadata
- Feature flags platform
- Knowledge base (Confluence/Runbooks)

Each server entry must include: owner, scope, RBAC model, logging location, data sensitivity, and rollback procedures.

## Allowlist Process

1) Intake: Request form with purpose, data classes, repositories, expected usage, vendor details.
2) Security Review: Data handling, network topology, compliance attestations, logging.
3) Pilot Approval: Timeboxed cohort, kill switch, success metrics.
4) Production Approval: Steady‑state SLOs, on‑call ownership, incident runbook.
5) Periodic Review: Every 60 days; re-verify scope, telemetry, exceptions.

## Exceptions (Rule-Bending) with Required Controls

- External indexing of code: Only for pilot repos, encryption at rest, SSO/SCIM, DLP checks, explicit approval.
- BYOK agents: Corporate keys via gateway; allowlists; logging; rate limits; isolated repos; emergency revoke.
- Third-party plugins: Signed and pinned; provenance logs; MCP mediation preferred.

## Operational Runbooks

- Key rotation and credential hygiene
- Failure modes and kill switch activation
- Incident response: containment, post-incident review, corrective actions
- Capacity and rate limit tuning
- Audit export and eDiscovery requests

## KPIs

- % of agent actions mediated by MCP
- 100% logging coverage for tool invocations
- Zero PII/data residency violations
- Time to approve new MCP server integrations
- MTTR for MCP incidents
