---
title: Metrics and ROI
layout: default
---

# Metrics and ROI

Last updated: YYYY-MM-DD

## KPI Framework (Pilot Scorecards)
- Flow efficiency
  - PR lead time (first commit → merge)
  - Review cycle time (ready-for-review → approval)
  - Merge frequency (per developer/week)
- Quality
  - Unit/integration test coverage (∆ points)
  - Escaped defects / hotfixes
  - Mutation score (if applicable)
- Agent effectiveness
  - Suggestion acceptance rate
  - Post-accept edits to green tests
  - Multi-file task completion rate; rollback ≤5%
- Security & governance
  - PII/secret egress incidents (target: 0)
  - % agent/tool actions with audit logs (target: 100%)
- Financials
  - ROI per seat (time saved * loaded rate – costs)
  - $/KLOC improved; toil hours reduced

## Instrumentation Plan
- IDE/Agents
  - Capture suggestion acceptance, completion length, time-to-accept
  - Tag multi-file tasks; record success/rollback
- SDLC Systems
  - PR metadata, review timing, merge stats
  - CI coverage reports; test outcomes
- Security/Governance
  - Policy gateway logs; PII/secret redaction events
  - MCP server logs; tool invocation traces to SIEM/data lake
- Normalization
  - Use control cohorts; exclude outage periods; attribute conservatively with overlap

## Targets & Decision Gates
- Proceed: cycle time ≥15% improvement; coverage +5 pts; rollback ≤5%; zero PII egress; full audit logs
- Remediate: policy gaps; rework 5–10%; partial auditability
- Stop: negative ROI after remediation or critical security findings

## Reporting Cadence
- Weekly: pilot scorecards
- Biweekly: leadership summaries
- 60‑day: roadmap review; trend analysis and refresh

## Dashboards (to link)
- Flow and Quality dashboards
- Agent acceptance and task analytics
- Security policy and egress monitoring
- Financial savings and cost accounting
