---
title: Vendor Capability Matrix (Slide)
layout: default
---

# Vendor Capability Matrix (Top 6)

Last updated: YYYY-MM-DD

Instructions
- Fill cells with Yes/No/Partial and attach citation IDs from Appendix (e.g., [GHC-DOCS-02], [SG-SEC-01]).
- Notes should briefly capture fit, constraints, and rule-bending controls if any.

## Legend
- Enterprise: SSO/SCIM, RBAC, Audit Logs, Data Residency, Private/VPC, Compliance (SOC2/ISO), On‑prem/Self-host, Policy SDK, MCP Support
- Security/Gov: Prompt filtering, Secret/PII redaction, Indexing controls, Tool allowlist, Signed/provenance
- Telemetry: Acceptance APIs, Task analytics, SIEM export
- Ops/Cost: Seat, Usage/Inference, Rate limits, SLAs

## Matrix

| Vendor | IDE | CLI | Personal Agent | Spec/Planning | Code Intelligence | CI/CD | Review/Test Gen | KB/RAG | SSO/SCIM | Audit Logs | Private/VPC | Compliance | On‑prem/Self-host | Policy SDK | MCP Support | Telemetry APIs | Cost Model | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| GitHub Copilot + Agent Mode | Yes [GHC-DOCS-02] | Partial (Tasks) [GHC-REL-01] | No | No | Partial (GH search) | Yes (GH Actions) | Partial (PR) | Partial (GHKB) | Yes [GHC-SEC-01] | Yes [GHC-SEC-01] | Yes (GHE) | Yes | N/A | Policies via GH | Indirect via integrations | Partial (API) | Seat/Usage | Baseline IDE; optimize & measure |
| Sourcegraph Cody/Amp (+ CLI) | Yes [SG-DOCS-02] | Yes [SG-DOCS-02] | No | No | Yes [SG-DOCS-01] | Integrates | Partial | Yes (Docs/KB) | Yes [SG-SEC-01] | Yes [SG-SEC-01] | Yes | Yes [SG-SEC-01] | Yes | Extensions | Likely via server | Events | Seat/Usage | Code-intel backbone; self-host |
| Anthropic Claude Code CLI | No | Yes [ANT-DOCS-02] | No | No | Partial | Integrates | Partial | No | Via gateway [ANT-SEC-01] | Via gateway | Private via gateway | See site | BYOM | Gateway policies | Via policy/MCP | N/A | Usage | Strong reasoning; enforce gateway |
| Google Gemini Code CLI | No | Yes [GGL-DOCS-02] | No | No | Partial | Integrates (GCP) | Partial | No | Yes [GGL-SEC-01] | Yes [GGL-SEC-01] | Private endpoints | Yes | Vertex (self-serve) | SDKs | Via gateway/MCP | APIs | Usage | Vendor diversity; validate posture |
| Amazon Q Developer/CLI | Yes (IDE) [AMZ-DOCS-01] | Yes [AMZ-DOCS-02] | No | No | Partial | Yes (AWS) [AMZ-SEC-01] | Partial | Partial | Yes [AMZ-SEC-01] | Yes | Private endpoints | Yes | AWS self-host | SDKs | Via gateway/MCP | APIs | Seat/Usage | Best for AWS-centric |
| Cursor | Yes [CUR-DOCS-01] | Partial | No | No | Partial | Integrations | Partial | No | See vendor [CUR-SEC-01] | Partial | Vendor-managed | See vendor | No | N/A | Via gateway/MCP | N/A | Seat | IDE alternative; refactor workflows |

## Decision Criteria (Reminders)
- Proceed: cycle time ≥15% improvement; coverage +5 pts; rollback ≤5%; zero PII egress; full audit logs
- Remediate: policy gaps; partial auditability; rework 5–10%
- Stop: negative ROI after remediation or critical security findings
