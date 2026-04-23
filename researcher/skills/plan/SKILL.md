---
name: plan
description: Use when the user has a goal but no scope/metric/verify configuration. Interactive 5-step wizard that converts plain-language goals into validated, ready-to-execute autoresearch configs.
---

# Plan — Goal → Config Wizard

The hardest part of autoresearch isn't the loop — it's defining Scope, Metric, and Verify
correctly. This skill walks the user through 5 mechanical gates before any optimization runs.

## When to activate

- User invokes `/autoresearch:plan`
- User says "I want to improve X but don't know what metric to use"
- User asks for help setting up an autoresearch run

## The 5 gates

1. **Capture goal** — plain-language statement of what to improve
2. **Define scope** — glob patterns must resolve to actual files
3. **Define metric** — must output a single number
4. **Define direction** — higher-is-better or lower-is-better
5. **Validate verify command** — dry-run must succeed and produce a parseable number

Every gate is mechanical. If a gate fails, revise and re-validate. Do not proceed to
`/autoresearch` until all 5 gates pass. Output a complete inline config block the user
can paste into their next command.
