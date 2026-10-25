---
name: systematic-debugging
description: Investigate software bugs by reproducing failures, gathering evidence, testing hypotheses, identifying root causes, and verifying minimal fixes. Use when debugging errors, failing tests, unexpected behavior, or regressions.
---

# Systematic Debugging

## Objective

Identify the root cause of a defect using reproducible evidence, then implement and verify the smallest complete fix.

## Procedure

### 1. Establish the facts
- Inspect the Git working tree and preserve unrelated user changes.
- Determine whether the failure exists on the current baseline before attributing it to a new change.
- Identify the affected component, expected behavior, actual behavior, and impact.
- Inspect relevant code, errors, stack traces, logs, tests, and configuration.
- Separate confirmed facts from assumptions.
- Identify the smallest useful reproduction before making changes.

### 2. Reproduce the failure
- Prefer a minimal, deterministic reproduction over a large end-to-end scenario.
- Record the command, relevant environment details, and observed result.
- Run the narrowest relevant test or reproduction first.
- Check whether the failure is consistent.
- If reproduction fails, investigate environmental, timing, configuration, and data differences.
- If reproduction is impossible, document the missing evidence and label any remaining hypotheses.

### 3. Trace the root cause
- Follow the relevant control flow and data flow.
- Check input validation, state transitions, boundaries, error handling, concurrency, and external dependencies where relevant.
- Form a specific hypothesis that explains the evidence.
- Choose an experiment that could disprove the hypothesis.
- Revise the hypothesis when evidence contradicts it.
- Avoid unrelated changes that make cause and effect difficult to establish.

### 4. Implement the smallest complete fix
- Follow existing repository conventions and preserve unrelated behavior.
- Avoid broad refactoring and unnecessary dependencies.
- Add a regression test that fails before the fix and passes after it, when practical.
- Do not modify files until the failure is understood, except for controlled experiments that are necessary and authorized.
- Before destructive commands, database changes, external requests, or other consequential actions, assess the impact and obtain authorization when required.

### 5. Verify the fix
- Re-run the original reproduction or targeted test.
- Run relevant regression tests, then broader checks as appropriate.
- Verify important negative cases, boundaries, error paths, and relevant security properties.
- Distinguish pre-existing failures from failures introduced by the change.
- Review the final diff for unintended changes, leaked secrets, debug code, unrelated edits, and weakened tests.
- If a check cannot run, record the limitation instead of implying it passed.

### 6. Report honestly

Summarize:
- The root cause and supporting evidence, distinguishing confirmed findings from hypotheses.
- Files changed and the reason for each change.
- The fix and its expected effect.
- Tests and commands actually executed, with their results.
- Checks that failed, were skipped, or could not run.
- Remaining uncertainty and risks.

## Rules

- Never invent test results or claim verification that did not occur.
- Never claim a root cause is confirmed when the evidence is insufficient.
- Do not delete or weaken meaningful tests merely to make them pass.
- Do not overwrite unrelated user changes.
- Do not perform destructive or consequential actions without appropriate authorization.
- Prefer evidence, reproducibility, and minimal changes over confidence or speed.

## Completion criteria

The investigation is complete when the root cause is supported by evidence, the fix addresses it, relevant verification has been performed or its limitations disclosed, and the final changes have been reviewed.