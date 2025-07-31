---
title: AI Tooling Governance, Policy, and Exceptions
layout: default
---

# AI Tooling Governance, Policy, and Exceptions

Scope: Governance for AI developer tooling at Nationwide with a focus on verifiable controls, measurable outcomes, and explicit documentation where rules are bent for innovation. Populate citations in the Appendix with first‑party sources.

Last updated: YYYY-MM-DD

## Objectives

- Ensure safe, compliant, and measurable adoption of AI agents across the SDLC.
- Provide a repeatable path from pilot to production with clear decision gates.
- Maintain auditability and incident readiness for all AI-assisted activities.

## Policy Principles

- Least-privilege access and data minimization.
- Measurability-first: pilots must declare KPIs and success thresholds.
- Defense-in-depth: network isolation, prompt firewalling, secret/PII redaction.
- Interoperability via MCP; preference for signed, mediated integrations.
- Vendor resilience: BYOK/BYOM behind policy abstractions; avoid hard lock-in.

## Approval Tiers

- Greenlist: Fully approved for production use within defined scope.
- Yellowlist: Pilot-only with timebox, controls, and kill-switch.
- Redlist: Blocked (insufficient controls or risk profile).

## Intake and Approval Workflow

1) Request Intake
   - Purpose, scope, repositories, data classes, vendor info, deployment model.
2) Security & Compliance Review
   - Data flow, network topology, compliance attestations, logging/audit.
3) Pilot Approval (Yellowlist)
   - Cohort definition, duration, KPIs, rollback/kill-switch plan, MCP mediation.
4) Production Approval (Greenlist)
   - SLOs, on-call ownership, incident runbooks, change management alignment.
5) Periodic Review (60-day cycle)
   - Metrics trend, incidents, scope drift, exceptions renewal or retirement.

## Required Controls (Baseline)

- Identity/Access: SSO/SCIM, RBAC, short‑lived credentials.
- Network: Private endpoints/VPC; egress mediation through enterprise gateway; no direct public LLM calls from developer endpoints.
- Data: Encryption at rest for any code indexing; repo scoping; PII/secret redaction.
- Governance: Signed, pinned extensions; provenance; MCP mediation preferred.
- Observability: 100% logging of agent actions/tool calls to SIEM/data lake; correlation IDs.

## Exceptions (Where Rules May Bend) and Conditions

- BYOK Personal Agents (Cline/Roo Code/Kilo Code)
  - Allowed only with corporate keys through a policy gateway.
  - Tool invocation allowlist; logging; rate limits; kill-switch.
  - Initial scope limited to evaluation repos or mirrored subsets.
- External Code Indexing/Search
  - Pilot-only with encryption at rest; SSO/SCIM; repo scoping; DLP checks; no cross‑repo spillover.
- Third-Party Plugins
  - Must be signed and pinned; provenance logs; MCP mediation where possible.

## Decision Gates (Pilot → Production)

- Proceed: ≥15% cycle time improvement; ≤5% rollback/rework; coverage +5 pts; zero PII/data residency violations; full audit logs.
- Remediate: Policy gaps or 5–10% rework; incomplete auditability; hold for fixes and re‑test.
- Stop: Negative ROI after remediation or critical security findings.

## Incident Response and Kill Switch

- Centralized kill switch per tool/vendor; defined activation criteria.
- On-call ownership in the platform squad; documented escalation path.
- Post-incident review with corrective actions and timelines.

## Roles and Responsibilities

- AI Tooling Governance Committee: Policy, standards, vendor evaluation, exception approvals.
- Platform Squad: MCP broker, policy gateway integration, telemetry, SRE ownership.
- Security/Compliance: Data classification, attestations, audits, red-teaming.
- Product/Engineering: Pilot execution, KPI reporting, adoption enablement.

## Training and Enablement

- Role-based training for developers, reviewers, and SREs.
- Prompt patterns and “what good looks like” guidance.
- Office hours and feedback channels during pilots.
