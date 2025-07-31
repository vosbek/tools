---
title: Market Landscape
layout: default
---

# Market Landscape (Agentic AI for SDLC)

Last updated: YYYY-MM-DD

## Categories and Exemplars
- IDE/Editor agents: GitHub Copilot + Agent Mode; Cursor; JetBrains AI Assistant
- CLI agents: Anthropic Claude Code CLI; Google Gemini Code CLI; Amazon Q CLI; Qwen Coder CLI; Aider; Sourcegraph Amp CLI
- Personal/BYOK agents: Cline; Roo Code; Kilo Code
- Spec-first / Planning: Amazon Kiro (requirements-to-PR alignment)
- Code intelligence/search: Sourcegraph Cody/Amp (+ self-host search like Zoekt)
- Review/Quality agents: PR review bots; unit/integration test generation; security review
- CI/CD & DevOps agents: Amazon Q for DevOps; GitHub-integrated assistants; Jenkins agents
- Knowledge/RAG: Confluence/Jira connectors via MCP; internal KB, runbooks
- Governance/security: Prompt firewalls, policy gateways, audit/logging, egress controls
- Model/runtime strategy: BYOM endpoints, private networking, cost accounting, eval harnesses

## Buyer Criteria (Finance/Insurance Lens)
- Enterprise readiness: SSO/SCIM, RBAC, audit logs, data residency options, private endpoints/VPC, SOC2/ISO coverage, on‑prem/self-host
- Security/Governance: prompt filtering, PII/secret redaction, code indexing controls, signed extensions, provenance
- Interop: MCP support or policy gateway mediation; SDKs/APIs for automation
- Telemetry: acceptance analytics, task metrics, export to SIEM/data lake
- ROI: measurable cycle-time reduction, rework/rollback decrease, coverage uplift, Toil reduction
- TCO: license + inference + infra + enablement + support

## Shortlist (Top 6 for Current Evaluation)
- GitHub Copilot + Agent Mode (IDE baseline) [GHC-DOCS-01; GHC-REL-01; GHC-SEC-01]
- Sourcegraph Cody/Amp (+ CLI) (code intelligence/search + CLI) [SG-DOCS-01; SG-SEC-01]
- Anthropic Claude Code CLI (CLI multi-file tasks) [ANT-DOCS-02; ANT-REL-01]
- Google Gemini Code CLI (CLI multi-file tasks; model diversity) [GGL-DOCS-02; GGL-SEC-01]
- Amazon Q Developer/CLI (AWS-integrated dev/DevOps) [AMZ-DOCS-01; AMZ-SEC-01]
- Cursor (IDE alternative focused on refactoring workflows) [CUR-DOCS-01; CUR-REL-01]

## Competitive Notes (High-Level)
- Copilot + Agent Mode: Deep GitHub integration; strongest for baseline adoption; instrument for measurable ROI [GHC-DOCS-02].
- Sourcegraph Cody/Amp: Enterprise code-intel and search backbone; self-host options and CLI for large refactors [SG-SEC-01].
- Claude Code CLI vs Gemini Code CLI: Compare multi-file accuracy, rework rate, and latency; enforce policy gateways [ANT-SEC-01; GGL-SEC-01].
- Amazon Q: Best fit for AWS-centric pipelines; evaluate CI/CD assistant value and IDE parity [AMZ-REL-01].
- Cursor: Refactor workflows; quantify deltas vs Copilot to justify incremental value [CUR-REL-01].

## Risks and Mitigations
- Data leakage / residency: mandate private endpoints/gateways; redaction; allowlists; audits
- Shadow IT via BYOK: corporate keys, policy gateway, signed/pinned extensions, kill switches
- Vendor lock-in: MCP/policy abstraction; BYOM endpoints; standard telemetry
- Overlapping features: strict pilot scope and decision gates; normalize metrics
