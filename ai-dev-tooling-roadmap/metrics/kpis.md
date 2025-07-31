---
title: Metrics and KPIs
layout: default
---

# Metrics and KPIs

Scope: Definitions and targets for measuring AI-driven SDLC improvements at Nationwide. Use these for pilot scorecards, decision gates, and quarterly reviews.

Last updated: 2025-07-31

## KPI Summary (Targets for Pilots)

- Flow efficiency
  - PR lead time: -15% to -25%
  - Review cycle time: -20%
  - Merge frequency: +10–20%
- Quality
  - Unit/integration test coverage: +5–10 percentage points
  - Escaped defects (hotfixes): -15%
  - Mutation score: +5 pts (if applicable)
- Agent effectiveness
  - Suggestion acceptance rate: +10–20% relative improvement
  - Multi-file task success: ≥90% without rollback
  - Rework/rollback rate: ≤5%
- Compliance and governance
  - PII/secret egress incidents: 0
  - 100% audit logging of agent actions/tool calls
- Financial
  - ROI per seat: positive within 2 quarters
  - Cost per KLOC improved: downward trend
  - Toil hours reduced: +10–20% reclaimed time

## Metric Definitions (With Formulas & Instrumentation)

Flow metrics
- PR lead time
  - Definition: time from first commit to merge for feature/bugfix PRs.
  - Formula: median(merged_at - first_commit_ts) per team/repo, 14d rolling.
  - Instrumentation: GitHub GraphQL v4 (pullRequests -> timelineItems to infer first commit).
- Review cycle time
  - Definition: time from PR ready-for-review to approval and to merge.
  - Formulas: median(first_approval_at - pr_ready_at), median(merged_at - pr_open_at).
  - Instrumentation: REST v3 Reviews API; GraphQL reviewRequested/approved events.
- Merge frequency
  - Definition: merges per dev per week.
  - Formula: count(merged_prs)/active_developers.
  - Instrumentation: GraphQL PRs + org member mapping.

IDE/Agent metrics
- Suggestion acceptance rate
  - Definition: accepted completions / shown completions.
  - Formula: sum(ai_tokens_accepted)/sum(ai_tokens_offered) and snippet-level acceptance.
  - Instrumentation: IDE plugins (Copilot, Codeium, JetBrains AI, Continue) event hooks.
- Completion impact
  - Definition: edits after AI insertion to reach green.
  - Formula: avg(edit_operations_until_green).
  - Instrumentation: IDE telemetry + CI status.
- Multi-file task success
  - Definition: tasks touching ≥3 files completed without rollback.
  - Formula: completed_agent_tasks/total_agent_tasks.
  - Instrumentation: CLI/IDE agent logs with task_id, files_changed, exit_status.

Quality metrics
- Coverage delta
  - Definition: change in line/branch coverage on merge.
  - Formula: coverage_pct_current - coverage_pct_baseline.
  - Instrumentation: CI parsers (JaCoCo, Istanbul, Coverage.py, Cobertura).
- Mutation score
  - Definition: % of killed mutants.
  - Formula: killed_mutants/total_mutants.
  - Instrumentation: Pitest/Stryker outputs.
- Escaped defects
  - Definition: incidents requiring hotfix post-release within 14/30 days.
  - Formula: count(issues type=bug introduced_by=commit_in_window).
  - Instrumentation: Issue tracker + error monitoring (Sentry/New Relic).

Security/compliance metrics
- Secrets leakage blocks
  - Definition: prevented commits/prompts with secrets.
  - Formula: count(blocked_secret_events).
  - Instrumentation: gitleaks/trufflehog + gateway classifiers.
- Policy violations
  - Definition: blocked tool calls/prompts per week.
  - Formula: blocked_policy_events/total_requests.
  - Instrumentation: gateway pass/fail counters.
- Audit completeness
  - Definition: % agent actions with end-to-end trace IDs.
  - Formula: audited_events/total_agent_actions.
  - Instrumentation: SIEM query index=ai_gateway sourcetype=agent_action | stats count by action_type.

Financial metrics
- Per-seat ROI
  - Definition: (time saved * loaded rate – tool cost – infra cost) / seats.
  - Inputs: time saved = baseline_cycle_time - actual_cycle_time aggregated.
  - Instrumentation: join PR/IDE telemetry with finance seats & billing.
- Cost per KLOC improved
  - Definition: total monthly cost / KLOC modified with quality improvement.
  - Formula: (license_cost + model_cost + infra_cost) / KLOC_changed_with_tests.
  - Instrumentation: PR diff stats filtered by tests passing and defect thresholds.

## Data Sources

- Git hosting: PR/commit metadata (GraphQL v4, REST v3)
- CI/CD: pipeline durations, test coverage reports
- IDE/Agent telemetry: acceptance and completion analytics (event schemas)
- Security: DLP, secret scanners, SAST/SCA
- SIEM/Data lake: unified logs for agent actions and MCP/policy gateway calls
- HR/time: loaded cost rates for ROI calculations

## Dashboards and Reporting

- Pilot scorecards: weekly
- Executive summary: biweekly
- Quarterly roadmap review: every 60 days content refresh and KPI trend analysis

## Normalization and Controls

- Use control groups per pilot (similar teams, repo profiles).
- Exclude outliers caused by incidents/outages.
- Attribute improvements conservatively when multiple tools overlap.

## Decision Gates (Mapped to KPIs)

- Proceed: cycle time ≥15% improvement, coverage +5 pts, rework ≤5%, zero PII egress, full audit logs.
- Remediate: policy gaps or 5–10% rework; partial auditability.
- Stop: negative ROI after remediation or critical security findings.
