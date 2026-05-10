---
description: "GitHub workflow: branch rules, PR standards, git account routing"
globs:
alwaysApply: true
---

## Git Accounts

Three separate identities — always confirm the correct one before pushing or creating PRs.

| Account | Server | Use for |
|---|---|---|
| `[yourname]` | `git.soma.salesforce.com` | Internal Salesforce repos, customer work on Salesforce infrastructure |
| `[yourname_sfemu]` | `github.com` (EMU) | Customer work hosted on GitHub, FDE team repos |
| `[yourname]` | `github.com` (personal) | Open-source, public profile, personal projects |

**How to check:** Run `/git-repos` to see live remotes and current branches for all repos.

**Quick switch:**
```bash
gh auth switch --user [yourname]        # personal
gh auth switch --user [yourname_sfemu]  # Salesforce EMU
# git.soma uses Salesforce SSO — no manual switch needed
```

**Account by directory:**
- `customers/[project]/` → `git.soma.salesforce.com`
- `agentforce/voice/`    → `github.com` EMU
- `[yourname]-profile/`  → `github.com` personal

---

## GitHub Workflow

### Protected Branch Rules
- Main branch is **protected** — never push directly to `main`
- All changes go through PRs — no exceptions
- Always create a feature branch before starting work:
  ```bash
  git checkout -b feature/[descriptive-name]
  ```

### PR Standards
- Write a clear PR description — collaborators need context to approve
- Include: what changed, why, and any testing notes
- Keep PRs focused — one logical change per PR
- Don't leave WIP commits in the PR — squash or amend before requesting review

### Commit Conventions
- Write commit messages in imperative mood: "Add voice fallback handler" not "Added..."
- Never use `--no-verify` to bypass hooks
