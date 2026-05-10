# CLAUDE.md — /Users/[yourname]/code

This is the working root for all development. Global identity and cross-project rules are in `~/.claude/CLAUDE.md`. Rules for specific domains are in `.claude/rules/`.

## Directory Map

```
/Users/[yourname]/code/
├── customers/          ← Customer projects (one folder per customer)
├── agentforce/         ← Internal work: templates, POCs, reusable components
├── reference/          ← Living reference guides and articles
├── scratch/            ← Throwaway experiments and POCs
└── tasks/
    ├── todo.md         ← Active task tracking
    ├── wip.md          ← Open threads with resume prompts
    └── lessons.md      ← Accumulated lessons from past corrections
```

## Session Start Checklist

1. Read `tasks/wip.md` — surface any open thread relevant to the current request
2. Read `tasks/todo.md` — pick up in-progress work if applicable
3. Check `tasks/lessons.md` for the relevant project before writing any code
4. Confirm active Salesforce org with `sf org display` before any deploy

## Core Principles

1. **Simplicity first** — minimize blast radius of every change
2. **Root causes only** — no band-aids, no workarounds that hide the real issue
3. **Minimal impact** — only touch what the task requires
4. **Salesforce-native** — prefer declarative; use code when it's the right tool
5. **Verify before done** — never mark complete without proving it works in-org
6. **Flag uncertainty** — if unsure about current state of a tool, API, or behavior, say so

## Customer Projects

Each customer folder should have its own `CLAUDE.md` with:
- Active org alias and agent name
- Key files and where things live
- Open issues and what to do next
