---
title: Nationwide AI Developer Tooling Roadmap
layout: default
---

# Nationwide AI Developer Tooling Roadmap

Objective: lead Nationwide into measurable, compliant AI-accelerated SDLC, focusing on enterprise-ready capabilities with verifiable documentation and clear ROI.

Last updated: YYYY-MM-DD

## Principles

- Governed innovation with explicit exceptions
- Measurability-first (define KPIs per pilot)
- Defense-in-depth (private endpoints/gateways, logging, redaction, RBAC)
- Interoperability via MCP (Model Context Protocol)
- Vendor resilience (BYOK/BYOM behind policy abstractions)

## Current State

- GitHub Copilot + Agent Mode deployed; qualitative lift, limited measurable ROI across wider cohorts
- Cursor trial: incremental benefit, not transformative broad value

## 90-Day Plan (Overview)

- Phase 1: Copilot optimization + instrumentation (Weeks 0–2)
- Phase 2: MCP foundation + curated servers, logging, policy (Weeks 2–6)
- Phase 3: Differentiator pilots (CLI agents, BYOK agents, spec-first tools, review/test, refactor agents) (Weeks 4–10)
- Decision/Readout: Weeks 8–12 (normalized metrics, TCO, red-team results, shortlist)

See the full quarterly plan in [roadmap/quarterly.md](roadmap/quarterly.md).

## Governance and Risk

- AI governance scope expansion; policy allowlists; red-teaming and eval harness; signed extensions; centralized kill-switches

Details in [governance/policy.md](governance/policy.md).

## Metrics and Expected Outcomes

- Flow: PR lead time -15–25%; review cycle -20%
- Quality: test coverage +5–10 pts; escaped defects -15%
- Compliance: zero PII egress; 100% agent action auditability
- Financials: ROI per seat; cost/KLOC improved; toil hours reduced

Definitions and dashboards in [metrics/kpis.md](metrics/kpis.md).

## Vendor Landscape

- Modalities impacting SDLC: IDE/Editor, CLI agents, Personal/BYOK agents, Spec/Planning, Code Intelligence, CI/CD & DevOps, Knowledge/RAG, Governance/Security, Model/Runtime
- Capability matrix schema and vendor shortlist in [landscape/vendors.md](landscape/vendors.md).

## MCP Standards

- Enterprise MCP broker, allowlist, curated servers, logging, approvals, PII redaction
- Standards and integration patterns in [standards/mcp.md](standards/mcp.md).

## Citations

- Every claim in public materials maps to a first‑party source; vendor-asserted items labeled accordingly.
- See [appendix/citations.md](appendix/citations.md).
