---
name: reason
description: Adversarial refinement loop for subjective decisions where no objective metric exists. Use when the user needs to converge on architecture choices, product strategy, content quality, or design debates via blind judge panels.
---

# Reason — Adversarial Refinement

Extends autoresearch to subjective domains. The blind judge panel IS the fitness
function — it replaces `val_bpb` for decisions where no objective metric exists.

## When to activate

- User invokes `/autoresearch:reason`
- User asks "should we use X or Y" for an architectural / strategic decision
- User wants to refine a pitch, proposal, RFC, or design via adversarial review

## Loop

1. Generate-A — initial candidate
2. Critic attacks — strawman refutation
3. Author-B responds with a competing candidate
4. Synthesizer merges the strongest pieces
5. Blind judge panel picks winner — labels randomized to X/Y/Z
6. Winner becomes new A
7. Repeat until N consecutive wins (convergence) or iterations exhausted

## Key invariant

Every agent is a cold-start fresh invocation. No shared session, no history bleed.
Judges never see A/B/AB labels — only randomized X/Y/Z to prevent bias.

## Flags

- `--iterations N` — bounded mode
- `--judges N` — judge count (3-7, odd preferred)
- `--convergence N` — consecutive wins to converge (default: 3)
- `--mode` — convergent / creative / debate
- `--domain` — software, product, business, security, research, content
- `--chain` — chain converged output to any other autoresearch command

## Output

Creates `reason/{date}-{slug}/` with lineage.md, candidates.md, judge-transcripts.md,
reason-results.tsv, and handoff.json.
