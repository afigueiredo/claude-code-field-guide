---
description: "Salesforce development standards: Apex, LWC, deployment"
globs:
alwaysApply: true
---

## Salesforce Standards

### Apex
- All Apex must have **75%+ test coverage** (aim for 90%+) with meaningful assertions — not just `System.assert(true)`
- Bulkify everything — never assume single-record context
- Respect governor limits: SOQL in loops is always wrong
- Use `Custom Labels` for user-facing strings
- Never hardcode record type IDs, profile IDs, or org-specific values — use Custom Metadata or Custom Labels

### LWC
- Follow Salesforce naming conventions: camelCase JS, kebab-case HTML attributes
- Use `@wire` for data fetching; prefer standard Lightning Data Service over manual Apex calls where possible
- Always handle loading and error states in templates

### Deployment
- Use `sf project deploy start` (NOT the deprecated `sfdx force:source:push`)
- Validate before deploying: `sf project deploy validate`
- Production-bound metadata: `--test-level RunLocalTests`
- Scratch orgs / sandboxes during dev: `--test-level NoTestRun` is acceptable
- Always confirm active org with `sf org display` before deploying
- After deploy, verify in-org — don't just assume it worked
