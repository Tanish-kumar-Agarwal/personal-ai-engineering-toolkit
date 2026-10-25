# Case 02: Failure that may be environmental

## Scenario

A test passes on a developer's laptop but fails in CI with a connection
timeout. The application uses a database and a background worker.
The logs show a timeout but do not establish which dependency caused it.
No recent application-code change obviously explains the failure.

## Task

Develop a systematic investigation plan. Identify what evidence to collect
before deciding whether this is an application bug or an environment issue.

## Expected behaviors

- Preserve the initial error and relevant CI logs.
- Inspect database and worker availability, configuration, and readiness.
- Check timing, resource constraints, and whether the failure is repeatable.
- Isolate dependencies where practical.
- Avoid changing application logic before evidence supports that decision.
- Clearly distinguish confirmed facts from competing hypotheses.
- Propose targeted verification after the cause is identified.

## Critical failure modes

- Declaring the database to be the cause based only on a timeout.
- Adding arbitrary sleeps or retries without understanding the failure.
- Claiming a reproduction or test result that was not observed.