---
title: Trending AI Repositories (Last 60 Days + Next 60 Days Watchlist)
layout: default
---

# Trending AI Repositories

Scope: Curated list focused on developer/agentic AI and SDLC-impacting code repositories. Code repos only (no datasets/papers). This page is refreshed on a 60-day cadence and includes a forward watchlist for the next 60 days.

Last updated: 2025-07-31

Curation criteria
- Strong star delta/activity in the last 60 days
- Meaningful releases or features relevant to developer tooling/agents
- Clear README and enterprise-suitable licensing signals
- Community momentum (issues/discussions) with substance

Note: Replace placeholders with the current month’s selections during each refresh, and prune repos that lose momentum. Add citation IDs in Notes referencing Appendix when applicable.

---

## Last 60 Days

- deepseek-ai/DeepSeek-Coder — https://github.com/deepseek-ai/DeepSeek-Coder
  Notes: Model updates and code-focused variants; impacts local/hosted agent backends. Signals: [DS-REL-01] [DS-NL-01] [DS-COM-01]
- TabbyML/tabby — https://github.com/TabbyML/tabby
  Notes: Self-hosted completion server with active releases and plugin ecosystem. Signals: [TABBY-REL-01] [TABBY-DOCS-01]
- aider-ai/aider — https://github.com/aider-ai/aider
  Notes: Fast-moving CLI agent for structured diffs; broad model support. Signals: [AID-REL-01] [AID-DOCS-01]
- cline/cline — https://github.com/cline/cline
  Notes: Local-first autonomous VS Code agent; rapid iteration. Signals: [CLN-REL-01] [CLN-DOCS-01]
- continuedev/continue — https://github.com/continuedev/continue
  Notes: OSS IDE framework for BYOM with enterprise-friendly configs. Signals: [CONT-REL-01] [CONT-DOCS-01] [CONT-DOCS-02]
- microsoft/autogen — https://github.com/microsoft/autogen
  Notes: Multi-agent framework patterns for orchestrated coding tasks. Signals: [MSA-REL-01] [MSA-DOCS-01]
- QwenLM/Qwen-coder — https://github.com/QwenLM/Qwen-coder
  Notes: Qwen code models and CLI; growing ecosystem and releases. Signals: [QWEN-REL-01] [QWEN-DOCS-01]
- roocodehq/roocode — https://github.com/roocodehq/roocode
  Notes: Project-wide planning and iterative diff agent. Signals: [ROO-REL-01] [ROO-DOCS-01]
- kilocodehq/kilo — https://github.com/kilocodehq/kilo
  Notes: BYOK coding agent for VS Code; community experimentation. Signals: [KILO-REL-01] [KILO-DOCS-01]
- sourcegraph/zoekt — https://github.com/sourcegraph/zoekt
  Notes: Code search/indexing building blocks for internal code intelligence. Signals: [SGOSS-DOCS-01]

### Agents and Agent Frameworks
- Significant-Gravitas/AutoGPT — https://github.com/Significant-Gravitas/AutoGPT  
  Notes: Early agent framework; good for understanding tool invocation patterns and limitations.  
- langchain-ai/langgraph — https://github.com/langchain-ai/langgraph  
  Notes: Graph-based orchestration for agent state; helpful for deterministic multi-step dev workflows.  
- All-Hands-AI/OpenHands — https://github.com/All-Hands-AI/OpenHands  
  Notes: VS Code–centric autonomous dev agent; useful for comparing personal agent UX.  
- aider-ai/aider — https://github.com/aider-ai/aider  
  Notes: Diff-first CLI coding agent; aligns well with git-centric review in enterprise pilots.

### Evals and Benchmarks
- EleutherAI/lm-evaluation-harness — https://github.com/EleutherAI/lm-evaluation-harness  
  Notes: Standard harness; extend with code tasks to compare models/vendors.  
- bigcode-project/bigcode-evaluation-harness — https://github.com/bigcode-project/bigcode-evaluation-harness  
  Notes: Code generation evals to complement IDE/CLI acceptance metrics.  
- OpenAutoCoder/CodeBench — https://github.com/OpenAutoCoder/CodeBench  
  Notes: Repo-level challenges; useful for pilot success criteria.

### Next 60 Days Watchlist

- aws/amazonq-kiro and documentation space
  Notes: Spec-first dev agent onboarding patterns and integrations. Signals: [AMZ-KIRO-DOCS-01] [AMZ-KIRO-DOCS-02] [AMZ-KIRO-NL-01]
- OpenAI platform/devtools
  Notes: Tool-use and code workflows iterations; CLI/devtools patterns. Signals: [OAI-DOCS-01] [OAI-REL-01]
- JetBrains AI Assistant plugin updates
  Notes: IDE telemetry hooks and enterprise setup improvements. Signals: [JBAI-REL-01] [JBAI-DOCS-02]
- Codeium enterprise features
  Notes: Telemetry and security posture enhancements. Signals: [CODE-SEC-01] [CODE-REL-01]
- Continue.dev server-side features
  Notes: Enterprise-friendly control planes and metrics. Signals: [CONT-DOCS-02] [CONT-REL-01]
- Microsoft AutoGen recipes
  Notes: Improved patterns for review/test agents. Signals: [MSA-REL-01]
- Qwen coder evaluations
  Notes: Benchmarks against DS and others on coding tasks. Signals: [QWEN-REL-01]
- ollama/ollama — https://github.com/ollama/ollama  
  Notes: Local model runner; supports BYOM experiments and on-prem constraints.  
- vllm-project/vllm — https://github.com/vllm-project/vllm  
  Notes: High-throughput inference; candidate for private endpoints.  
- ray-project/ray — https://github.com/ray-project/ray  
  Notes: Distributed compute for agent workflows and serving.  
- microsoft/onnxruntime — https://github.com/microsoft/onnxruntime  
  Notes: Optimized inference; portable runtime for edge/on-prem.

### RAG and Code Intelligence
- sourcegraph/zoekt — https://github.com/sourcegraph/zoekt  
  Notes: Fast code search; baseline for enterprise code intelligence.  
- qdrant/qdrant — https://github.com/qdrant/qdrant  
  Notes: Vector DB; semantic code retrieval backends.  
- pgvector/pgvector — https://github.com/pgvector/pgvector  
  Notes: Embeddings in Postgres; low-friction infra path.  
- chroma-core/chroma — https://github.com/chroma-core/chroma  
  Notes: Developer-friendly vector store; prototype semantic context.

### Coding Tools and Dev UX
- cursor-so/cursor — https://github.com/cursor-so/cursor  
  Notes: AI IDE; relevant for IDE pilot comparisons vs GH Copilot.  
- github/copilot.vim — https://github.com/github/copilot.vim  
  Notes: Editor coverage; informs training and adoption patterns.  
- microsoft/TypeChat — https://github.com/microsoft/TypeChat  
  Notes: Type-guided NL→structured; safer tool calls in agents.

---

## Next 60 Days Watchlist

### Agents and Agent Frameworks
- OpenDevin/OpenDevin — https://github.com/OpenDevin/OpenDevin  
  Watch: Repo automation capabilities maturing; evaluate sandboxed trials.  
- anyscale/aviary (example) — https://github.com/ray-project/aviary  
  Watch: Multi-model serving for agent workflows.

### Evals and Benchmarks
- princeton-nlp/SWE-bench (if reactivated) — https://github.com/princeton-nlp/SWE-bench  
  Watch: Real-world software engineering tasks; useful benchmark inputs.  
- codellama/eval (example) — URL to be validated  
  Watch: Task-specific evals; map to pilot metrics.

### LLM Infrastructure
- modal-labs/llm-apps (example) — URL to be validated  
  Watch: Patterns for cost/perf in hosted/private serving.  
- llama.cpp — https://github.com/ggerganov/llama.cpp  
  Watch: Local inference improvements relevant to on-prem constraints.

### RAG and Code Intelligence
- marqo-ai/marqo — https://github.com/marqo-ai/marqo  
  Watch: Vector search innovation; code/doc retrieval scenarios.  
- deepset-ai/haystack — https://github.com/deepset-ai/haystack  
  Watch: RAG pipelines and connectors; MCP server candidates.

### Coding Tools and Dev UX
- sourcegraph/sg (dev tooling) — https://github.com/sourcegraph/sg  
  Watch: Developer ergonomics around Sourcegraph stack.  
- microsoft/gpt-commit-summarizer (example) — URL to be validated  
  Watch: Commit/PR summarization; wire into review workflows.

---

## Refresh Checklist (Every 60 Days)

1) Update window: past_60 and next_60; set Last updated date.  
2) Re-run selection using GitHub Trending (code) and 60-day star delta + release activity.  
3) Validate enterprise suitability: license, security posture, maintenance.  
4) Add/remove repos based on momentum and relevance to our pilots.  
5) Cross-link to Roadmap where repos inform enablements/pilots.  
6) Submit changes via PR for governance review.
