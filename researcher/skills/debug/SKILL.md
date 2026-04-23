---
name: debug
description: Autonomous bug-hunting loop using the scientific method. Use when the user reports a bug, test failure, or unexpected behavior and wants iterative root-cause investigation across an entire codebase.
---

# Debug — Autonomous Bug Hunter

Doesn't stop at one bug — iteratively hunts ALL bugs in scope using falsifiable
hypotheses, evidence-based investigation, and 7 investigation techniques.

## When to activate

- User invokes `/autoresearch:debug`
- User describes a symptom: crash, failing test, wrong output, performance regression
- User wants to find the root cause, not just patch the symptom

## Loop

1. Gather symptoms (reproduction steps, error messages, scope)
2. Recon — map the error surface
3. Hypothesize — specific, testable, falsifiable
4. Test — ONE experiment per iteration
5. Classify — confirmed / disproven / inconclusive
6. Log finding with code evidence (file:line + repro steps)
7. Repeat until iterations exhausted or all hypotheses resolved

## Techniques

Binary search, differential debugging, minimal reproduction, trace execution,
pattern search, working backwards, rubber duck.

Every disproven hypothesis is logged — equally valuable. Chain with `--fix` to
auto-switch to the fix loop after hunting.
