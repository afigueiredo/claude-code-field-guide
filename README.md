# salesforce-claude-skills

A layered Claude Code configuration system for Salesforce and Agentforce developers. Extracted from production FDE workflows.

Companion to the article: [Claude Code Doesn't Forget](https://medium.com/@afigueiredo)

---

## What's in here

A set of templates that implement the four-layer configuration system described in the article. Copy, adapt, and use as a starting point for your own setup.

```
templates/
├── layer1-global-identity/
│   └── CLAUDE.md              ← ~/.claude/CLAUDE.md
├── layer2-working-root/
│   └── CLAUDE.md              ← ~/code/CLAUDE.md
├── layer3-domain-rules/
│   ├── workflow.md            ← Planning, execution, self-improvement loop
│   ├── salesforce.md          ← Apex, LWC, deployment standards
│   ├── agentforce.md          ← Topics, actions, Trust Layer, voice patterns
│   └── github.md              ← PR workflow, branch rules, git account routing
├── layer4-project-context/
│   └── CLAUDE.md              ← customers/[project]/CLAUDE.md
├── memory/
│   ├── MEMORY.md              ← Memory index template
│   └── project_example.md     ← Project memory entry template
└── agents/
    └── regression-analyst.md  ← Subagent for diagnosing regressions
```

---

## How the layers work

Claude Code loads every `CLAUDE.md` from `~/.claude/` down to your current working directory. All matching layers load simultaneously.

| Layer | File | Loaded when |
|---|---|---|
| 1 — Global identity | `~/.claude/CLAUDE.md` | Always |
| 2 — Working root | `~/code/CLAUDE.md` | Any session under `/code/` |
| 3 — Domain rules | `~/code/.claude/rules/*.md` | Any session under `/code/` |
| 4 — Project context | `customers/[project]/CLAUDE.md` | Inside that project only |

**Memory** (`~/.claude/projects/<hash>/memory/`) handles volatile state — current project status, open issues, preferences — separately from config, which handles stable rules.

---

## Quick start

1. Copy `layer1-global-identity/CLAUDE.md` to `~/.claude/CLAUDE.md` and fill in your identity, preferences, and cross-project rules.

2. Copy `layer2-working-root/CLAUDE.md` to your code root (e.g. `~/code/CLAUDE.md`) and update the directory map.

3. Copy `layer3-domain-rules/` to `~/code/.claude/rules/`. Keep what's relevant, remove what isn't, add your own.

4. For each customer or project, copy `layer4-project-context/CLAUDE.md` into that project's directory and fill in the active org, agent name, and open issues.

5. Copy `memory/MEMORY.md` to `~/.claude/projects/<path-hash>/memory/MEMORY.md` as your index starting point.

---

## Subagents

The `agents/` directory contains a general-purpose `regression-analyst` subagent. Copy it to `~/.claude/agents/` to use it.

It reads session transcripts, eval reasoning, and live configuration to diagnose why specific sessions are failing — and produces exact before/after changes ready to apply. Useful for any project with automated eval runs.

---

## More

- Article: [Claude Code Doesn't Forget]([https://medium.com/@afigueiredo](https://afigueiredo.medium.com/claude-code-doesnt-forget-a-layered-configuration-system-for-serious-projects-a8eac8047526?postPublishedType=repub))
- Profile: [@afigueiredo](https://medium.com/@afigueiredo)
- More skills and tools: coming soon

---

`Claude Code` `Salesforce` `Agentforce` `Developer Tools` `LLM` `AI Agents`
