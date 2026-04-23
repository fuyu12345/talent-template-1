---
name: ship
description: Universal shipping workflow with mechanically verifiable checklists. Use when the user wants to ship a code PR, deployment, release, blog post, email campaign, sales deck, research paper, or design asset.
---

# Ship — Universal Shipping Workflow

Ship anything through 8 phases: Identify → Inventory → Checklist → Prepare →
Dry-run → Ship → Verify → Log.

## When to activate

- User invokes `/autoresearch:ship`
- User says "ship it", "deploy", "release", "publish", "send"
- User wants pre-flight validation before any irreversible action

## Workflow

1. **Identify** — auto-detect what's being shipped
2. **Inventory** — list every artifact involved
3. **Checklist** — generate domain-specific, mechanically verifiable items
4. **Prepare** — resolve every blocker before proceeding
5. **Dry-run** — validate without irreversible side effects
6. **Ship** — execute the actual deployment / publish / send
7. **Verify** — confirm the artifact reached its destination and behaves correctly
8. **Log** — record outcome, links, monitoring window

## Supported types

code-pr, code-release, deployment, content, marketing-email, marketing-campaign,
sales, research, design.

## Flags

- `--dry-run` — validate but don't ship
- `--auto` — auto-approve if checklist passes
- `--force` — skip non-critical items (blockers still enforced)
- `--rollback` — undo last ship action
- `--monitor N` — post-ship monitoring for N minutes
- `--checklist-only` — just check readiness, do nothing
