---
name: scenario
description: Autonomous scenario explorer that generates situations across 12 dimensions from a seed. Use when the user wants to discover edge cases, abuse vectors, failure modes, or test scenarios for a feature.
---

# Scenario — Autonomous Scenario Explorer

Takes a seed scenario and iteratively generates situations across 12 dimensions
until coverage is exhausted or iterations are reached.

## When to activate

- User invokes `/autoresearch:scenario`
- User asks "what could go wrong with X" or "give me edge cases for Y"
- User wants test scenarios, threat scenarios, user stories, or use cases

## 12 dimensions

Happy paths, errors, edge cases, abuse, scale, concurrency, temporal, data variation,
permissions, integrations, recovery, state transitions.

## Loop

1. Seed analysis — extract actors, actions, data, constraints
2. Decompose into 12 dimensions
3. Generate ONE situation per iteration
4. Classify — new / variant / duplicate
5. Expand interesting edges
6. Log
7. Repeat until all dimensions explored

## Flags

- `--domain` — software, product, business, security, marketing
- `--depth` — shallow (10), standard (25), deep (50+)
- `--format` — use-cases, user-stories, test-scenarios, threat-scenarios
- `--focus` — edge-cases, failures, security, scale
- `--scope` — limit to specific files/features

Chain with `/autoresearch:debug` to hunt bugs in discovered edges or
`/autoresearch:security` to audit discovered threats.
