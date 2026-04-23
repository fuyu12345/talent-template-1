# Core Skill

This is the agent's primary skill. It defines the agent's main capability
and working methodology.

## Guidelines

- Follow the instructions in the agent's system prompt
- Apply domain expertise as described in the agent profile
- Maintain the agent's defined personality and communication style
- Deliver outputs that match the agent's role and specialization

## Autoresearch Loop (Default)

When invoked without a subcommand, run the unbounded modify → verify → keep/discard loop:

1. Read current state, git history, and results log
2. Pick the next change based on what worked, failed, or is untried
3. Make ONE focused change
4. Git commit before verification (`experiment:` prefix)
5. Run mechanical verification (tests, benchmarks, scores)
6. If improved → keep. If worse → `git revert`. If crashed → fix or skip
7. Log the result in TSV format
8. Repeat until interrupted or `Iterations: N` is reached

Required setup before looping: Goal, Scope, Metric, Direction, Verify command.
Use `AskUserQuestion` to collect any missing context before execution.
