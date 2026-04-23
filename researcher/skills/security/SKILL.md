---
name: security
description: Read-only security audit using STRIDE threat modeling, OWASP Top 10 sweeps, and red-team adversarial analysis. Use when the user wants a structured security report with code evidence for every finding.
---

# Security — Autonomous Security Audit

Read-only by default. Produces structured findings with file:line evidence and
attack scenarios. No theoretical fluff — every finding must be reproducible.

## When to activate

- User invokes `/autoresearch:security`
- User asks for a security review, threat model, or vulnerability scan
- User wants OWASP / STRIDE coverage of an application or service

## Workflow

1. Codebase recon — discover entry points, dependencies, secrets
2. Asset inventory — what's worth attacking
3. Trust boundary mapping
4. STRIDE threat model (Spoofing, Tampering, Repudiation, Info disclosure, DoS, Elevation)
5. Attack surface map
6. Autonomous testing loop — one hypothesis per iteration
7. Red-team adversarial analysis with 4 hostile personas
8. Structured report

## Output

Creates `security/{date}-{slug}/` with 7 files: summary, findings, threat-model,
attack-surface, recon, evidence log, and remediation plan.

## Flags

- `--diff` — only audit files changed since last audit
- `--fix` — opt into auto-remediation of confirmed Critical/High findings
- `--fail-on <severity>` — exit non-zero for CI/CD gating
