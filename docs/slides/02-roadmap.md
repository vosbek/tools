---
title: 90-Day AI Dev Tooling Plan
layout: default
---

# 90-Day Roadmap (Leadership-Ready)

Audience: SVP/CTO and Governance Committee. Objective: secure and maximize current investments, enable differentiating capabilities, then pilot future bets with measurable ROI and full auditability.

Last updated: 2025-07-31

---

## Executive Summary (What we will do in 90 days)

- Secure and optimize Copilot + Agent Mode across baseline teams with hard metrics and governance.
- Enable platform capabilities that raise all boats: policy gateway, MCP servers, code search backbone, telemetry.
- Pilot differentiating tools in small cohorts with clear decision gates: CLI code agents, personal/BYOK agents, spec-first tooling.
- Report measured ROI and compliance status every 2 weeks; refresh vendor/market view every 60 days.

---

## Phase 1 (Weeks 1–3): Harden Baseline and Make It Measurable

Why
- Today’s Copilot usage shows qualitative gains; we need quantitative improvements and governance guarantees.

Do
- Copilot optimization playbook: prompt hygiene, repo context, policy alignment [GHC-DOCS-01; GHC-SEC-01].
- Define and implement KPIs and instrumentation (see Metrics): acceptance rate, PR lead/review time, rework, coverage deltas.
- Governance hardening: corporate keys only, audit logging to SIEM, secrets/PII redaction patterns.
- Baseline cohorts: 3–5 teams across Java/.NET/Python.

Deliverables
- Weekly scorecards and acceptance dashboards.
- Baseline report vs prior month for the same cohorts.
- Risk log with policy exceptions and remediations.

Decision Gate A (exit Phase 1)
- Acceptance ≥ 25% sustained, review cycle −15%, audit completeness 100% (see metrics/kpis).

---

## Phase 2 (Weeks 2–7, overlaps): Enablements That Unlock Value

Why
- Platform capabilities let any agent/tool operate safely and observably; they reduce integration friction.

Do
- Policy Gateway: prompt firewall (PII/secret redaction), RBAC, tool allowlist, audit schema -> SIEM.
- MCP servers: connect code search, KBs, and tools via standard protocol [MCP-DOCS-01].
- Code Intelligence backbone: Sourcegraph (enterprise or OSS Zoekt) for semantic search and context [SG-DOCS-01; SGOSS-DOCS-01].
- PR Review/Test agents: enable category tools with thresholds and audit [REVQA-NL-01].
- Telemetry: normalize IDE/CLI agent events; join with PR/CI for outcomes (see metrics/kpis).

Deliverables
- Gateway live for pilot repos; MCP services catalog; search indexed for target repos.
- Integrated dashboards for flow, quality, agent effectiveness, compliance, and cost.

Decision Gate B (enter Phase 3)
- ROI per seat ≥ 20%; rework ≤ 5%; coverage delta ≥ +3 pts; zero confirmed PII egress.

---

## Phase 3 (Weeks 6–13): Differentiating Pilots (Small, Measurable)

Tracks (run 2–3 in parallel, 2–4 teams each)

1) CLI Code Agents
- Tools: Claude Code, Gemini Code, Amazon Q CLI, Qwen Coder, Aider, Sourcegraph Amp [ANT-DOCS-02; GGL-DOCS-02; AMZ-DOCS-02; QWEN-DOCS-01; AID-DOCS-01; SG-DOCS-02].
- Targets: multi-file task success, cycle time reduction, rollback ≤ 5%.
- Governance: route via gateway; private endpoints; per-task audit.

2) Personal/BYOK Agents
- Tools: Cline, Roo Code, Kilo Code, Continue.dev [CLN-DOCS-01; ROO-DOCS-01; KILO-DOCS-01; CONT-DOCS-01].
- Targets: autonomy ratio, oversight time, acceptance uplift.
- Controls: corporate keys only, repo isolation, kill-switch, audit.

3) Spec-first / Planning
- Tool: Amazon Kiro (requirements-to-PR) [AMZ-KIRO-DOCS-01; AMZ-KIRO-DOCS-02].
- Targets: PR review cycle time −20%, rework ≤ 5%.
- Scope: AWS-heavy teams; evaluate portability limits.

4) Self-hosted Completion (Optional)
- Tool: Tabby/TabbyML [TABBY-DOCS-01].
- Targets: acceptance vs hosted; latency/cost; governance control.
- Scope: limited repos with model swap hooks.

Deliverables
- Pilot readouts with KPIs and cost per KLOC improved.
- Executive recommendation per track: scale, iterate, or stop.

---

## Risks and Controls (Finance/Insurance)

- Data egress and PII: enforce prompt redaction and VPC/private endpoints [OAI-SEC-01; AMZ-SEC-01].
- Audit and forensics: 100% SIEM coverage of agent actions; immutable logs.
- Identity and access: SSO/SCIM, RBAC scopes by repo/team; tool allowlist signed extensions.
- Vendor lock-in: BYOM/BYOK strategy; MCP abstraction; multi-cloud endpoints.
- Cost spikes: model usage alerts; budget caps; rollout throttle by cohort.

---

## Resourcing and Timeline

- Core team: 1 platform eng, 1 SRE, 1 security (policy gateway), 1 data eng (telemetry), 1 PM.
- Cohorts: 6–12 teams total across phases; 2–4 per track in Phase 3.
- Cadence: weekly pilot scorecards; biweekly exec updates; 60‑day landscape refresh.

---

## What We Will Not Do (Q3)

- Broad rollouts without metrics and audit.
- Unvetted autonomous agents on sensitive repos.
- Vendor commitments without 2–3 pilot readouts.

---

## Appendix Links (Key)

- Vendors & Matrix: /landscape/vendors/
- Deep Dives: /landscape/tools/
- Metrics & KPIs: /metrics/kpis/
- Governance & Policy: /governance/policy/
- Standards (MCP): /standards/mcp/
- Citations: /appendix/citations/
