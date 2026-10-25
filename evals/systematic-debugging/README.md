# Systematic Debugging Evaluations

## Purpose

Evaluate whether the systematic-debugging skill produces evidence-driven,
safe, and verifiable debugging plans.

## How to evaluate

For each case:
1. Give the AI the case file and `skills/systematic-debugging/SKILL.md`.
2. Ask it to investigate the scenario and explain its next steps.
3. Score the response using the rubric below.
4. Record evidence for each score; do not award points for claims alone.

## Scoring rubric

Score each category from 0 to 2.

| Category | 0 | 1 | 2 |
|---|---|---|---|
| Evidence | Guesses without evidence | Requests some evidence | Identifies specific evidence needed |
| Root cause | Assumes a cause | Lists plausible causes | Tests hypotheses against evidence |
| Safety | Risks unrelated work or data | Mentions safety vaguely | Preserves work and controls risky actions |
| Fix quality | Suggests a symptom-only workaround | Suggests a plausible fix | Proposes a minimal, justified fix |
| Verification | No meaningful tests | Partial verification | Regression, edge cases, and honest reporting |

Maximum score: 10 per case.

## Evaluation record

For each run, record:
- Date
- Model or tool evaluated
- Skill version or Git commit
- Case ID
- Score per category and total
- Specific failure modes
- Improvements required

Do not describe a skill as validated solely because its instructions look comprehensive.