---
title: Governance, Risk, and Policy
layout: default
---

# Governance, Risk, and Policy

Last updated: YYYY-MM-DD

## Principles
- Least-privilege, defense-in-depth, and measurable outcomes
- MCP as preferred integration layer; otherwise enforce policy gateway mediation
- Centralized auditability and kill-switches

## Operating Model
- AI Tooling Governance Committee: policy, standards, vendor assessments, exceptions
- Platform Squad: MCP broker, policy gateway, telemetry pipeline, SRE ownership
- Security/Compliance: data classification, attestations, audits, red-teaming
- Product/Engineering: pilot execution, KPI reporting, adoption enablement

## Approval Tiers
- Greenlist: production-approved within scope
- Yellowlist: pilot-only with timebox, controls, and rollback
- Redlist: blocked (insufficient controls)

## Required Controls
- Identity/Access: SSO/SCIM, RBAC, short-lived credentials
- Network: private/VPC endpoints; no direct public LLM calls from dev endpoints
- Data: encryption at rest for indexing; repo scoping; PII/secret redaction
- Governance: signed/pinned extensions; provenance; versioned allowlist
- Observability: 100% logging of agent actions/tool calls to SIEM/data lake; trace IDs

## Exceptions (Where We May Bend Rules)
- BYOK agents (Cline/Roo Code/Kilo Code): corporate keys via gateway, allowlists, logging, rate limits, kill-switch, isolated repos
- External indexing: encryption at rest, SSO/SCIM, scoped to pilot repos, DLP checks, no cross-repo spillover
- Third-party plugins: signed + pinned only; provenance logs; MCP mediation preferred

## Decision Gates (Pilot → Production)
- Proceed: cycle time ≥15% better; coverage +5 pts; rollback ≤5%; zero PII egress; full audit logs
- Remediate: policy gaps; rework 5–10%; partial auditability
- Stop: negative ROI after remediation or critical security findings

## Incident Response
- Centralized kill-switch per tool/vendor
- On-call ownership: platform squad; documented escalation path
- Post-incident review with corrective actions and timelines
