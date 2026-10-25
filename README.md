# Personal AI Engineering Toolkit

A portable, modular library of engineering skills and evaluation cases designed to improve AI-assisted software development through evidence, safe changes, and verifiable results.

## Goals

- Investigate bugs using evidence rather than guesses.
- Make minimal, maintainable changes that preserve existing behavior.
- Improve testing, security reviews, architecture decisions, and code quality.
- Evaluate skill behavior against explicit scenarios and measurable criteria.
- Keep skills independent of any single AI model, editor, or agent framework.

## Repository structure

```text
personal-ai-engineering-toolkit/
|-- skills/
|   `-- systematic-debugging/
|       `-- SKILL.md
|-- evals/
|   `-- systematic-debugging/
|       |-- README.md
|       |-- case-01-regression.md
|       |-- case-02-environment-failure.md
|       `-- case-03-risky-fix.md
|-- workflows/
|-- adapters/
|-- docs/
`-- README.md
```

## Current skills

### Systematic Debugging

Location: `skills/systematic-debugging/SKILL.md`

Provides a structured process for establishing facts, reproducing failures, testing hypotheses, implementing minimal fixes, verifying results, and reporting uncertainty honestly.

Evaluation cases: `evals/systematic-debugging/`

## Evaluation principles

- Score observable behavior, not confident wording.
- Require evidence for root-cause claims.
- Check that unrelated changes and important data are protected.
- Distinguish proposed tests from tests actually executed.
- Record limitations and failure modes.
- Improve skills when evaluations reveal weaknesses.

See `evals/systematic-debugging/README.md` for the current evaluation rubric.

## Design principles

1. **Modular:** Each skill has a focused responsibility.
2. **Portable:** Skills should work across compatible AI tools with minimal adaptation.
3. **Evidence-driven:** Recommendations should be grounded in inspectable evidence.
4. **Safe by default:** Preserve user work and avoid unauthorized destructive actions.
5. **Verifiable:** Claims about fixes and tests must match what was actually checked.
6. **Continuously evaluated:** A well-written skill is not automatically a proven skill.

## Development status

This is an early-stage project. The first skill and its evaluation scenarios are being established. Evaluation results, additional skills, integrations, and automated tooling will be added only when implemented and checked.

## Contributing

When improving a skill:

1. Keep its purpose and scope clear.
2. Prefer precise, actionable instructions over generic advice.
3. Add or update evaluation cases for meaningful behavioral changes.
4. Review the diff for unrelated edits and accidental disclosure of secrets.
5. Report verification honestly, including failures and skipped checks.