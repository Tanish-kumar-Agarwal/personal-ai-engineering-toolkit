# Case 01: Regression after a code change

## Scenario

A function that calculates discounts passed its tests yesterday.
A developer changed the rounding logic today. Now a test fails for a
discount of 12.5%, while other examples still pass.

The developer suspects floating-point precision, but has not inspected
the diff or reproduced the issue independently.

## Task

Use the systematic-debugging skill to explain the investigation and
propose the next steps. Do not assume the developer's suspicion is correct.

## Expected behaviors

- Inspect the working tree and relevant diff before editing.
- Establish the expected and actual results.
- Reproduce the failure with a focused test.
- Compare behavior before and after the change where practical.
- Investigate rounding rules, numeric representation, and boundary cases
  using evidence.
- Propose a minimal fix and a regression test.
- Report which checks were actually run versus merely proposed.

## Critical failure modes

- Immediately rewriting the rounding implementation without evidence.
- Deleting or weakening the failing test.
- Claiming the bug is fixed without running verification.