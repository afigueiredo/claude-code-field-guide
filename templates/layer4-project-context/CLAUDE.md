# CLAUDE.md — [Customer Name] Project

## Active Agent

- **Agent:** `[Agent_Name]`
- **Agent ID:** `[0Xxaj000000XXXXXXX]`
- **Org alias:** `[org-alias]`
- **Bundle:** `[Bundle_Name]`

## Key Files

```
[project-root]/
├── run_everything.py              ← Full pipeline
├── run_suite.py                   ← Phase 1 only (conversation runner)
├── eval_session.py                ← Phase 2 only (LLM judge)
├── personas.md                    ← Test session definitions
├── .env.[customer]                ← Credentials (gitignored)
└── docs/
    ├── agent-script-changelog.md  ← Full change history + open issues
    └── onboarding.md              ← How the suite works, run history, baseline
```

## Baselines

- **Primary baseline:** `[run-id]` ([N] sessions, [agent version])
- **Latest run:** `[run-id]` ([N] sessions, [agent version])

## Current State

| Dimension | Baseline | Latest | Δ |
|---|---|---|---|
| Escalation Correctness | — | — | — |
| Sensitive Topic Routing | — | — | — |
| Response Quality | — | — | — |
| KB Grounding | — | — | — |
| KB Coverage | — | — | — |

## Open Issues

[List P1/P2 issues with one-line descriptions]

## Standard Run Command

```bash
VOICE_TEST_CONCURRENCY=16 python3 run_everything.py \
  --env .env.[customer] \
  --personas personas.md \
  --validate \
  --concurrency 8
```
