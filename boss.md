# Nationwide AI Developer Tooling – 90-Day Concurrent Plan
Version: 2025-07-31

## Executive Summary
- Objective: Run three workstreams in parallel for the next 90 days to achieve measurable productivity and quality gains with enterprise-grade governance.
- Workstreams (Concurrent):
  - A) Copilot Optimization and Measurement
  - B) Governance & Enablement Layer (MCP + Policy + Telemetry)
  - C) Differentiator Pilots (CLI agents, BYOK/personal agents, spec-first)
- Outcomes Target (ranges): PR lead time -15–25%; review cycle -20%; coverage +5–10 pts; escaped defects -15%; zero PII egress; 100% agent action auditability; positive ROI per seat.

## Guiding Principles
- Governed innovation with explicit exceptions and auditability
- Measurability-first: defined KPIs with shared instrumentation
- Defense-in-depth: private endpoints, policy gateway, redaction, RBAC
- Interoperability: Model Context Protocol (MCP) as the integration fabric
- Vendor resilience: BYOK/BYOM via policy abstractions to avoid lock-in

## Scope: 90-Day Concurrent Workstreams

### A) Copilot Optimization and Measurement
- Standardize Copilot workflows and prompts; publish team playbooks.
- Enable acceptance telemetry and correlate agent sessions with PRs.
- Expand CI signals: coverage delta per PR, lint/security gates.
- Deliverables:
  - Baseline productivity/quality dashboard (initial baseline by week 2–3, then rolling updates)
  - Acceptance-rate and usage heatmaps by team/repo
  - Copilot playbook and recommended practices

### B) Governance & Enablement Layer (MCP + Policy + Telemetry)
- MCP broker with curated enterprise servers and server allowlist.
- Policy gateway: prompt firewall, PII/secret redaction, RBAC, tool/connector allowlist, kill-switch.
- Central audit schema; ship to SIEM (actor, repo, branch, file list, tool invocations, allow/deny decisions).
- Network posture: private endpoints/VPN/VPC; model routing through a broker.
- Deliverables:
  - MCP + curated servers online; documented integration pathway
  - Policy/ruleset deployed, with exceptions workflow and expirations
  - SIEM dashboards for audit and compliance

### C) Differentiator Pilots (CLI, BYOK/Personal Agents, Spec-First)
- CLI Agents: Claude Code, Qwen Coder, Aider, Sourcegraph Cody/Amp (for refactor/migration scale and code intelligence).
- BYOK/Personal Agents: Cline, Roo Code, Kilo, Continue.dev (dev-owned automation with enterprise guardrails).
- Spec-First: Amazon Kiro (spec-to-code workflows for structured changes).
- Pilot design: 2–3 squads per tool category, with explicit entry/exit criteria, shared KPIs, and cost/usage telemetry under governance.
- Deliverables:
  - Pilot reports (productivity, quality, compliance, and TCO)
  - Comparative analysis and shortlist for staged rollout

## KPIs and Instrumentation (Common)

### Flow/Throughput
- PR Lead Time = merged_at − first_commit_time (target -15–25%)
- Review Cycle = merged_at − first_review_time (target -20%)
- Cycle Time with Agent Sessions (IDE/agent events → PR)

### Quality
- Coverage Delta per PR (+5–10 pts in targeted modules)
- Escaped Defects (incidents/bugs per KLOC; -15%)
- Static/security finding trends normalized by KLOC

### Agent Effectiveness
- Acceptance Rate = accepted_tokens / suggested_tokens
- Multi-file Task Success (≥2 files changed per agent task closed)

### Compliance/Security
- Egress Incidents: zero PII/secret egress to external LLMs
- Audit Completeness: 100% agent actions logged with identity, repo, files, tools

### Financials
- ROI per Seat = (hours saved × blended rate − tool cost) / seat
- Cost per KLOC Improved = tool cost / KLOC with quality uplift

### Data Sources
- GitHub REST/GraphQL for PR timing; CI parsers for coverage
- IDE/agent telemetry APIs; policy gateway logs; SIEM for audits

## Governance & Security Controls
- Policy Gateway: prompt firewall, PII/secret redaction, RBAC, tool allowlist, kill-switch
- Identity: SSO/SCIM; device posture checks
- Supply Chain: signed extensions; SBOM; static scanning on agent code
- Exceptions: time-bounded approvals with owner and scope; attestation
- Audit: standardized schema; dashboards for usage and exceptions

## Vendor Landscape (Representative)
- IDE Assistants: GitHub Copilot/Agent Mode (baseline), JetBrains AI Assistant, Codeium, Tabby (self-hosted)
- CLI/Code Intelligence: Claude Code, Qwen Coder, Aider, Sourcegraph Cody/Amp (+Zoekt)
- BYOK/Personal Agents: Cline, Roo Code, Kilo, Continue.dev
- Spec-First: Amazon Kiro
- Review/Test Agents: auto-review/test-generation; integrate under policy and audit

## Risks and Mitigations
- PII/Secret Leakage: policy redaction, private endpoints, allowlists, SIEM alerts
- Shadow IT: SSO/SCIM, device posture, blocked unapproved endpoints, visible allowlist
- Lock-in: BYOK/BYOM abstraction, MCP layer
- Overhype/Underutilization: KPI gating, standard pilot templates, controlled scope
- Compliance Gaps: mandatory audit schema; weekly control reviews

## Resourcing and Cost (Illustrative)
- Core platform/governance team: program lead, security architect, platform engineer, data/telemetry analyst
- Pilots: 2–3 squads per category (CLI, BYOK, spec-first), 2–3 weeks minimum per pilot cycle
- Costs: seats/licenses for candidate tools, model/API usage, SIEM/logging

## Decision Framework (While Concurrent)
- Fortnightly readouts per workstream with shared KPI format
- Gate A (~Week 4–6): Continue, pivot, or halt at pilot level, per KPIs/security
- Gate B (~Week 8–12): Shortlist for staged rollout; retire or contain others

## Executive Asks (Immediate)
- Approve the concurrent execution of all three workstreams for 90 days
- Approve budget for seats, API usage, and SIEM/logging uplift
- Approve governance controls: MCP broker, policy gateway and redaction, SIEM logging, allowlists, and kill-switches
- Approve pilot matrix (tools × squads) with shared KPIs and gates