---
name: predict
description: Multi-persona prediction — simulates 5 expert reviewers (Architect, Security Analyst, Performance Engineer, Reliability Engineer, Devil's Advocate) who debate code and reach consensus. Use before debugging, fixing, or shipping.
---

# Predict — Multi-Persona Prediction

One-shot analysis from 5 expert perspectives in ~2 minutes. Each persona is
invoked cold-start, independently analyzes the code, then they debate and
converge on a ranked finding list.

## When to activate

- User invokes `/autoresearch:predict`
- User asks for a code review from "multiple angles" or "expert opinions"
- User wants pre-flight analysis before running another autoresearch command

## The 5 personas

1. **Architect** — design, coupling, cohesion, future maintainability
2. **Security Analyst** — STRIDE / OWASP exposure, untrusted input handling
3. **Performance Engineer** — latency, throughput, allocations, hot paths
4. **Reliability Engineer** — failure modes, retries, idempotency, observability
5. **Devil's Advocate** — assumptions, missing tests, what could break

## Output

Ranked list of findings, each tagged by persona, with file:line evidence and
suggested follow-up. Designed to chain directly into other autoresearch commands.

## Chain patterns

- `--chain debug` — pre-ranked hypotheses fed into the debug loop
- `--chain security` — multi-persona red team analysis
- `--chain scenario,debug,fix` — full quality pipeline
