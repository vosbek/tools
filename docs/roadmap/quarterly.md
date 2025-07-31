---
title: 90-Day Roadmap
layout: default
---

# 90-Day Roadmap

Timeframe: Weeks 0–12  
Objective: Measurable improvements in SDLC throughput, quality, and compliance with verifiable, enterprise-ready tooling.

Last updated: YYYY-MM-DD

## Executive Summary

- Phase 1 (Weeks 0–2): Harden GitHub Copilot/Agent Mode, baseline KPIs, developer enablement.
- Phase 2 (Weeks 2–6): Enablements of the tools we already have access to (not only MCP). This includes MCP foundation, policy gateway integration, telemetry, and first-party tool enablements (Copilot Agent Mode advanced workflows, GH Actions assistants, code search/RAG, review/test agents, and knowledge integrations).
- Phase 3 (Weeks 4–10): Controlled pilots for differentiators (CLI agents, BYOK agents, spec-first tools, migration/refactor agents).
- Weeks 8–12: Normalize metrics, TCO/security review, shortlist recommendation, staged rollout plan.

## Milestones and Deliverables

### Weeks 0–2: Baseline and Copilot Hardening
- Deliverables
  - Copilot/Agent Mode standard configuration (org policy, repo indexing boundaries).
  - Prompt/usage guide and short training modules.
  - KPI dashboards: acceptance rate, time-to-PR, review cycle duration.
- KPIs (Baseline Capture)
  - Suggestion acceptance (%), median completion length, time-to-accept.
  - PR lead time, review cycle time, merge frequency.
  - Zero critical policy violations.

### Weeks 2–6: Enablements (Beyond MCP)
Enable tools already available to us with governance and telemetry. MCP is one part of this enablement track.

- Deliverables
  - MCP foundation
    - Enterprise MCP broker and allowlist.
    - 3–6 curated MCP servers (code search, Jira/Boards, CI/CD, KB/Confluence, feature flags, SAST/SCA metadata).
    - Policy: audit logging, PII redaction, approvals, signed integrations.
  - Policy Gateway & Telemetry
    - Prompt firewall and redaction integrated for IDE/CLI agents.
    - SIEM/data lake sink for all agent/tool actions (IDE/CLI/API).
  - First-Party Tool Enablements (Examples)
    - GitHub Copilot Agent Mode advanced workflows (repo maintenance tasks, test generation flows).
    - GitHub Actions assistants (template actions for build/test/release; PR checks surfaced to agents).
    - Enterprise code search/RAG (e.g., Sourcegraph as code-intel backbone with repo scopes).
    - PR Review/Test Agents (enable baseline review automations and test gen where feasible).
    - Knowledge integrations (Jira/Confluence read-only connectors for context retrieval).
- KPIs
  - % of agent/assistant actions with full audit logging.
  - Adoption: % of teams using at least one enablement workflow per week.
  - Zero PII/data residency violations.
  - Reduction in manual toil: ≥10% decrease for targeted workflows (e.g., test boilerplate, changelog drafting).

### Weeks 4–10: Differentiator Pilots
- Tracks and Targets
  - CLI Agents: Claude Code, Gemini Code, Amazon Q CLI, Qwen Coder, Aider, Sourcegraph Amp CLI  
    - Metric: time to complete medium multi-file change; rework rate; accuracy.
  - BYOK Personal Agents (via corporate keys/policy): Cline, Roo Code, Kilo Code  
    - Metric: multi-step task completion rate; oversight time; rollback frequency.
  - Spec-First Tools: Amazon Kiro and peers  
    - Metric: pre-implementation defect discovery; spec→PR coherence; review time reduction.
  - Review/Test Agents: PR review automation and unit/integration test generation  
    - Metric: coverage delta (+5–10 pts target); review cycle reduction (-20% target).
  - Migration/Refactor Agents: controlled codemods  
    - Metric: cycle time improvement; test pass rate; rollback <5%.
- Cohorts
  - CLI: 25–50 devs; 3–4 squads across Java/.NET/Python/TypeScript.
  - BYOK: 20–40 devs; 2–3 squads; eval repos and policy gateway.
  - Spec-first: 5–10 teams with active feature work.

### Weeks 8–12: Readout and Decision
- Deliverables
  - Normalized metrics across pilots with control groups.
  - TCO model: license + inference + infra + enablement + support.
  - Security red-team and governance assessment.
  - Shortlist and staged rollout with required controls and exceptions.
- Decision Gates
  - Proceed: cycle time ≥15% improvement, rework ≤5%, coverage +5 pts, zero PII egress, full audit logs.
  - Remediate: policy gaps, accuracy-driven rework 5–10%, partial auditability.
  - Stop: negative ROI after remediation or critical security gaps.

## Risks and Controls (Where Rules May Bend)
- BYOK Agents: Allowed only through corporate keys via policy gateway; allowlist tools; logging; rate limits; kill-switch; isolated repos for pilots.
- External Code Indexing: Encryption at rest; SSO/SCIM; scoped to pilot repos; disable cross-repo spillover; DLP checks.
- Model Endpoints: Use private/VPC endpoints or enterprise gateway; no direct public calls from developer endpoints.
- Third-Party Plugins: Require signed, pinned versions; provenance logs; MCP mediation preferred.

## Metrics Dictionary
- Engineering Flow: PR lead time; review cycle time; merge frequency.
- IDE/Agent: suggestion acceptance; post-accept edits; multi-file task success; rollback rate.
- Quality: coverage delta; mutation score (if available); escaped defects/hotfixes.
- Security: secrets leakage blocks; policy violations; SAST/SCA trend.
- Financial: ROI per seat; $/KLOC improved; toil hours reduced.

## Dependencies and Resourcing
- Platform squad: MCP broker, policy gateway integration, telemetry pipeline.
- Security: policy, redaction, audit requirements; exception approval.
- Enablement: training content and office hours.
- Data: access to SDLC telemetry and SIEM.
