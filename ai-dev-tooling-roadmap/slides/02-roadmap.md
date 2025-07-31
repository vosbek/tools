---
title: 90-Day Roadmap
layout: default
---

# 90-Day Roadmap

Last updated: YYYY-MM-DD

## Phases at a Glance
- Phase 1 (Weeks 0–2): Optimize GitHub Copilot/Agent Mode and baseline KPIs
- Phase 2 (Weeks 2–6): Enablements (beyond MCP): policy gateway, telemetry, advanced Copilot workflows, code search/RAG backbone, review/test agents, knowledge integrations
- Phase 3 (Weeks 4–10): Differentiator pilots (CLI agents, BYOK personal agents, spec-first tools, migration/refactor, review/test)
- Weeks 8–12: Decision/readout: normalized metrics, TCO, security assessment, staged rollout

## Phase 1 — Copilot Optimization & Baseline (Weeks 0–2)
- Standardize Copilot/Agent Mode settings and repo indexing boundaries
- Publish prompt/usage guide and short training modules
- Stand up KPI dashboards: acceptance rate, time-to-PR, review cycle duration, merge frequency
- Targets: capture baselines; zero critical policy violations

## Phase 2 — Enablements (Beyond MCP) (Weeks 2–6)
- MCP foundation: broker, allowlist, 3–6 curated servers (code search, Jira/Boards, CI/CD, KB/Confluence, feature flags, SAST/SCA)
- Policy gateway: prompt firewall, PII/secret redaction; all agent calls logged to SIEM/data lake
- First-party enablements:
  - Copilot Agent Mode advanced workflows (repo maintenance, test generation, docs updates)
  - GitHub Actions assistants (templated actions, PR checks surfaced to agents)
  - Code search/RAG backbone (e.g., Sourcegraph) with repo scoping and DLP controls
  - PR review/test agents where feasible; knowledge connectors (Jira/Confluence read-only)
- Targets: ≥10% toil reduction on targeted workflows; adoption % of teams using ≥1 enablement/week; zero PII violations

## Phase 3 — Differentiator Pilots (Weeks 4–10)
- CLI agents: Claude Code CLI, Gemini Code CLI, Amazon Q CLI, Aider, Sourcegraph Amp CLI
- BYOK personal agents: Cline, Roo Code, Kilo Code (corporate keys via policy gateway)
- Spec-first planning: Amazon Kiro (requirements→PR coherence)
- Migration/refactor agents: controlled codemods with tests and rollback
- Review/test agents: PR review automation and test generation
- Targets: cycle time ≥15% improvement vs control; rework/rollback ≤5%; coverage +5 pts

## Decision & Rollout (Weeks 8–12)
- Normalize metrics; TCO (license + inference + infra + enablement + support)
- Security red-team and governance review
- Shortlist recommendation; staged rollout plan with exception controls

## Decision Gates
- Proceed: cycle time ≥15% better; coverage +5 pts; rollback ≤5%; zero PII egress; full audit logs
- Remediate: policy gaps; rework 5–10%; partial auditability
- Stop: negative ROI after remediation or critical security findings
