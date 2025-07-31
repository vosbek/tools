---
title: Vendor Landscape and Capability Matrix
layout: default
---

# Vendor Landscape and Capability Matrix

Note: All citations reference Appendix IDs for verifiability. See [appendix/citations.md](../appendix/citations.md).

Scope: agentic AI developer experience tools impacting the SDLC. Content is structured for verifiable citations; populate the sources in the Appendix as first‑party links (docs, security pages, release notes) plus clearly labeled third‑party/community sentiment. Citation IDs follow the hyphenated scheme (e.g., GHC-DOCS-01) and map to [appendix/citations.md](../appendix/citations.md).

Last updated: 2025-07-31

## Categories (Modalities)

- IDE/Editor agents: GitHub Copilot + Agent Mode; Cursor; JetBrains AI Assistant; Codeium; Continue.dev; Tabby (IDE plugins)
- CLI agents: Claude Code CLI; Gemini Code CLI; Amazon Q CLI; Qwen Coder CLI; Aider; Sourcegraph Amp CLI; OpenAI DevTools
- Personal/BYOK dev agents: Cline; Roo Code; Kilo Code; Continue.dev (BYOK) via corporate keys/policy
- Spec-first/planning: Amazon Kiro and peers for requirements-to-PR alignment
- Code intelligence/search: Sourcegraph Cody/Amp; Zoekt/Sourcegraph OSS; internal embeddings/OpenSearch
- Review and quality: PR review automation; test generation (unit/integration); security code review agents
- CI/CD and DevOps agents: Amazon Q Developer/DevOps; GitHub-integrated assistants; Jenkins/GitLab agents
- Knowledge/RAG: Confluence/Jira connectors via MCP; internal KB/runbooks
- Governance/security: prompt firewalls/policy gateways; audit/logging; egress control
- Model/runtime strategy: BYOM endpoints; private networking; cost accounting; eval harnesses

## Capability Matrix Schema

Score each vendor across these columns with verifiable citations:

- Modality coverage: IDE | CLI | Personal Agent | Spec/Planning | Code Intelligence | CI/CD | Review/Test Gen | Knowledge/RAG
- Enterprise readiness: SSO/SCIM | RBAC | Audit Logs | Data Residency | Private Networking/VPC | Compliance (SOC 2, ISO 27001) | On‑prem/Self-host | Policy SDK | MCP Support
- Security/governance: Prompt filtering | Secret/PII redaction | Code indexing controls | Tool allowlist | Signed extensions/provenance
- Telemetry/analytics: Suggestion acceptance APIs | Task analytics | SIEM/Data lake integration
- Operations/cost: Seat license | Usage/inference costs | Rate limits/quotas | SLAs
- Notes: Constraints, exceptions required, or rule-bending controls; include citation IDs

## Matrix (Top 20 — add Yes/No/Partial + citation IDs)

| Vendor | IDE | CLI | Personal | Spec | Code Intel | CI/CD | Review/Test | KB/RAG | SSO/SCIM | Audit | Private/VPC | Compliance | On‑prem | Policy SDK | MCP | Telemetry APIs | Cost Model | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| GitHub Copilot + Agent Mode | Yes [GHC-DOCS-02] | Partial (via tasks) [GHC-REL-01] | No | No | Partial via GH code search | Yes (GH Actions) | Partial (PR review) | Partial (GHKB) | Yes [GHC-SEC-01] | Yes [GHC-SEC-01] | Yes (GH Enterprise) | Yes (attestations) | N/A | Policies via GH | MCP Indirect | Partial (API) | Seat/Usage | Baseline in GH |
| Sourcegraph Cody/Amp (+ CLI) | Yes [SG-DOCS-02] | Yes [SG-DOCS-02] | No | No | Yes [SG-DOCS-01] | Integrates | Partial | Yes | Yes [SG-SEC-01] | Yes [SG-SEC-01] | Yes | Yes [SG-SEC-01] | Yes | Yes (ext) | MCP via server | Yes (events) | Seat/Usage | Code intel at scale |
| Anthropic Claude Code CLI | No | Yes [ANT-DOCS-02] | No | No | Partial | Integrates | Partial | No | Via gateway [ANT-SEC-01] | Via gateway | Private endpoints | See site | BYOM | Via gateway | MCP via broker | N/A | Usage | Reasoning strong |
| Google Gemini Code CLI | No | Yes [GGL-DOCS-02] | No | No | Partial | Integrates (GCP) | Partial | No | Yes [GGL-SEC-01] | Yes | Private endpoints | Yes | Vertex | SDKs | MCP via gateway | APIs | Usage | Validate posture |
| Amazon Q Developer/CLI | Yes [AMZ-DOCS-01] | Yes [AMZ-DOCS-02] | No | No | Partial | Yes (AWS) [AMZ-SEC-01] | Partial | Partial | Yes [AMZ-SEC-01] | Yes | Private endpoints | Yes | AWS | SDKs | MCP via gateway | APIs | Seat/Usage | AWS-centric strength |
| Cursor | Yes [CUR-DOCS-01] | Partial | No | No | Partial | Integrations | Partial | No | See vendor [CUR-SEC-01] | Partial | Vendor-managed | See vendor | No | N/A | MCP via gateway | N/A | Seat | IDE alternative |
| JetBrains AI Assistant | Yes [JBAI-DOCS-01] | No | No | No | Partial | Integrates | Partial | No | Yes [JBAI-SEC-01] | Yes | Private options | Yes | N/A | SDK | MCP via gateway | IDE telemetry | Seat | Changelog [JBAI-REL-01], demo [JBAI-YT-01], community [JBAI-COM-01] |
| Codeium | Yes [CODE-DOCS-01] | Yes (CLI) | No | No | Partial | Integrates | Partial | No | Yes [CODE-SEC-01] | Yes | Private options | Yes | Some | SDK | MCP via gateway | APIs | Seat/Usage | Releases [CODE-REL-01], community [CODE-COM-01], news [CODE-NL-01] |
| Continue.dev | Yes [CONT-DOCS-01] | Yes (local CLI) | Yes (BYOK) | No | Partial | Integrates | Partial | No | N/A | N/A | Local-first | N/A | Self-host via BYOM | Ext | MCP via gateway | Local metrics | OSS/Free | Enterprise config [CONT-DOCS-02], releases [CONT-REL-01], community [CONT-COM-01] |
| Tabby/TabbyML | Yes (plugins) [TABBY-DOCS-01] | Yes (server) | No | No | Partial | Integrates | No | No | N/A | N/A | Self-host | N/A | Yes (self-host) | API | MCP via gateway | Server metrics | Infra cost | Releases [TABBY-REL-01], demo [TABBY-YT-01], community [TABBY-COM-01] |
| Aider | No | Yes [AID-DOCS-01] | No | No | Partial | Integrates | Partial | No | N/A | N/A | Local-first | N/A | Self-host via BYOM | N/A | MCP via gateway | N/A | OSS | Releases [AID-REL-01], demos [AID-YT-01], community [AID-COM-01] |
| Cline | Yes (plugin) [CLN-DOCS-01] | Yes (local) | Yes (BYOK) | No | Partial | Integrates | Partial | No | N/A | N/A | Local | N/A | BYOM | Ext | MCP via gateway | Local | OSS | Releases [CLN-REL-01], discussion [CLN-COM-01], newsletter [CLN-NL-01] |
| Roo Code | Yes (plugin) [ROO-DOCS-01] | Yes (local) | Yes (BYOK) | No | Partial | Integrates | Partial | No | N/A | N/A | Local | N/A | BYOM | Ext | MCP via gateway | Local | OSS | Releases [ROO-REL-01], demos [ROO-YT-01], community [ROO-COM-01] |
| Kilo Code | Yes (plugin) [KILO-DOCS-01] | Yes (local) | Yes (BYOK) | No | Partial | Integrates | Partial | No | N/A | N/A | Local | N/A | BYOM | Ext | MCP via gateway | Local | OSS | Releases [KILO-REL-01], community [KILO-COM-01] |
| Qwen Coder CLI | No | Yes [QWEN-DOCS-01] | No | No | Partial | Integrates | Partial | No | N/A | N/A | Private endpoints | See vendor | BYOM | SDK | MCP via gateway | APIs | Usage | Releases [QWEN-REL-01], newsletter [QWEN-NL-01], community [QWEN-COM-01] |
| OpenAI DevTools/Code features | Yes (plugins) [OAI-DOCS-01] | Yes (CLI/tools) | No | No | Partial | Integrates | Partial | No | See site [OAI-SEC-01] | Partial | Private endpoints | See site | BYOM | SDK | MCP via gateway | APIs | Usage | Release notes [OAI-REL-01], demos [OAI-YT-01], community [OAI-COM-01] |
| Microsoft AutoGen/AutoDev | No | Yes [MSA-DOCS-01] | No | No | Partial | Integrates | Partial | No | N/A | N/A | Self-host | N/A | Self-host | SDK | MCP via gateway | Logs | OSS | Releases [MSA-REL-01], demos [MSA-YT-01], community [MSA-COM-01] |
| Amazon Kiro (Spec-first) | No | No | No | Yes [AMZ-KIRO-DOCS-01] | No | Integrates | Partial | Partial | Yes (AWS) | Yes | Private | Yes | AWS | SDK | MCP via gateway | APIs | TBD | Getting started [AMZ-KIRO-DOCS-02], news [AMZ-KIRO-NL-01], community [AMZ-KIRO-COM-01] |
| Sourcegraph OSS (Zoekt/etc.) | No | Yes [SGOSS-DOCS-01] | No | No | Yes | Integrates | No | No | N/A | N/A | Self-host | N/A | Yes | API | MCP via server | Logs | Infra cost | Building blocks |
| Review/Test Agents (generic) | IDE hooks | CI hooks | No | No | No | Yes | Yes | No | N/A | Yes | Private | See vendor | N/A | SDK | MCP via gateway | APIs | Seat/Usage | Category placeholder |

Populate the table with “Yes/No/Partial” and include citation IDs (e.g., [GHC‑DOCS‑01]) referencing Appendix/Citations.

## Shortlist for Pilot Tracks (Initial)

- CLI Agents: Claude Code CLI, Gemini Code CLI, Amazon Q CLI, Aider, Sourcegraph Amp CLI
- IDE Baseline: GitHub Copilot + Agent Mode (optimization and metrics)
- Code Intelligence/Search: Sourcegraph Cody/Amp (enterprise deployment considerations)
- IDE Alternative: Cursor (focused cohorts)

Populate the table with “Yes/No/Partial” and include citation IDs (e.g., [GHC‑DOCS‑01]) referencing Appendix/Citations.

## Shortlist for Pilot Tracks (Initial)

- CLI Agents: Claude Code CLI, Gemini Code CLI, Amazon Q CLI, Aider, Sourcegraph Amp CLI
- IDE Baseline: GitHub Copilot + Agent Mode (optimization and metrics)
- Code Intelligence/Search: Sourcegraph Cody/Amp (enterprise deployment considerations)
- IDE Alternative: Cursor (focused cohorts)

## Evaluation Rubric (Per Pilot)

- Accuracy and rework: rollback rate ≤5%
- Productivity: cycle time improvement ≥15% vs control
- Quality: coverage uplift ≥5 pts; defect trend improvement
- Governance: 100% audit logs; zero PII egress; policy adherence
- Operability: SSO/SCIM, private endpoints, SIEM integration
- TCO: license + inference + infra + enablement + support
