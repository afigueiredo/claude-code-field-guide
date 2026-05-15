---
description: "GitHub workflow: branch rules, PR standards, git account routing"
globs:
alwaysApply: true
---

## Git Accounts

Separate identities — always confirm the correct one before pushing or creating PRs.

| Account | Server | Use for |
|---|---|---|
| `[personal-user]` | `github.com` | Open-source, public profile, personal projects |
| `[work-user]` | `github.com` | Company or customer work hosted on GitHub |
| `[internal-user]` | `[internal-git-host]` | Private repositories on an internal git host |

**How to check:** Run `/git-repos` to see live remotes and current branches for all repos.

**Quick switch:**
```bash
gh auth switch --user [personal-user]  # personal
gh auth switch --user [work-user]      # work
# Internal git hosts may use SSO or a separate credential helper.
```

**Account by directory:**
- `customers/[project]/` → `[internal-git-host]` or work GitHub
- `shared/[project]/`    → work GitHub
- `[yourname]-profile/`  → personal GitHub

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
