---
name: learn
description: Autonomous documentation engine. Scout codebase, generate or update docs, validate, and fix in a loop. Use when the user wants to create, refresh, or audit project documentation.
---

# Learn — Autonomous Documentation Engine

Scout → generate → validate → fix → repeat. Doc work is mechanically verifiable
when validation runs are present (dead links, missing references, stale examples).

## When to activate

- User invokes `/autoresearch:learn`
- User says "generate docs", "update docs", "check if docs are stale"
- New project needs initial documentation

## 4 modes

| Mode | Purpose |
|------|---------|
| `init` | Create documentation from scratch |
| `update` | Refresh existing docs against current code (uses git diff scoping) |
| `check` | Read-only health report on current docs |
| `summarize` | Quick high-level overview |

## Workflow

1. Project-type detection
2. Scale-aware codebase scouting
3. Dynamic doc discovery (`docs/*.md`)
4. Generate or update target docs
5. Validate — dead links, broken examples, drift from code
6. Fix loop — max 3 retries per doc
7. Cross-reference linking + auto-generated Mermaid diagrams

## Conditional outputs

API reference, testing guide, config guide, changelog, dependency docs.

## Flags

- `--mode` — init / update / check / summarize
- `--depth` — shallow / standard / deep
- `--file` — selective single-doc update
- `--format` — alternative output format
