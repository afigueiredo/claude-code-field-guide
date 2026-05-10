---
description: "Agentforce development: topics, actions, instructions, voice patterns"
globs:
alwaysApply: true
---

## Agentforce Context

### Core Constructs
- **Topics** — define the agent's scope; map to intent clusters
- **Actions** — discrete capabilities the agent can invoke (Apex, Flow, Prompt Template, MuleSoft, etc.)
- **Instructions** — natural language rules that govern agent behavior within a Topic
- **Prompt Templates** — structured prompts for grounding, summarization, or custom LLM calls
- **Data Cloud grounding** — retrieval-augmented generation using Data Cloud vector search

### Voice Implementation
- Latency-sensitive: minimize round trips; prefer synchronous actions where possible
- Handle turn-taking logic explicitly — don't assume the agent knows when the user has finished speaking
- Always define fallback handling for no-input and no-match conditions
- Test with real latency conditions, not just Studio previews

### Einstein Trust Layer
- No data retention by the LLM — calls via Trust Layer do not train models
- Data masking is active — PII is masked before leaving Salesforce boundary
- Audit trails are generated for all LLM invocations
- Trust Layer applies when invoked through Agentforce; direct API calls bypass it — know which path you're on

### Design Principles
- Prefer declarative (Flow, prompt templates) over code (Apex) where equally capable
- Agent actions should be single-purpose and composable — not monolithic
- Ground responses in Salesforce data; avoid hallucinated CRM context
