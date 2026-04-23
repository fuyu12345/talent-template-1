---
name: fix
description: Autonomous error-repair loop. Use when the codebase has failing tests, type errors, lint errors, or build errors and the user wants iterative atomic fixes until zero errors remain.
---

# Fix — Autonomous Error Crusher

Takes a broken state and iteratively repairs it until everything passes.
ONE fix per iteration. Atomic, committed, verified, auto-reverted on failure.

## When to activate

- User invokes `/autoresearch:fix`
- User says "fix all the failing tests/types/lint/build errors"
- User chains from `/autoresearch:debug --fix` or passes `--from-debug`

## Loop

1. Auto-detect what's broken (tests, types, lint, build)
2. Prioritize — blockers first
3. Fix ONE thing
4. Commit
5. Verify error count decreased
6. Guard check — no regressions in unrelated areas
7. Keep or revert
8. Repeat until error count hits zero (auto-stops, even unbounded)

## Constraints

- Never modify guard/test files when running with `--guard`
- Use `--category` to restrict to one error type at a time when scope is large
- Always commit before verifying so reverts are clean
