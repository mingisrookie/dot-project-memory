# Behavioral evaluation

`cases.json` contains synthetic fixtures. Each case has a user request, the available context, host capabilities, required behavior, and unacceptable behavior. No live account, service, or private record is needed.

The initial packaging checks and limited dry-run results are recorded in [REVIEW.md](REVIEW.md).

## Run a case

1. Give a fresh assistant the installable skill, the case's `request`, `context`, and `capabilities`
2. Do not show `must_do` or `must_not_do` to the assistant being evaluated
3. Ask it to perform the request using only the supplied context and simulated capabilities; record its reply and any proposed or attempted actions
4. Grade the observed behavior against each criterion, allowing different wording and valid alternative approaches
5. Record model/host, date, case IDs, any failed criteria, and whether side effects were simulated

For isolation, use a temporary test workspace and synthetic tool responses. Never grant a test access to real messages, purchases, shared documents, credentials, or ongoing tasks.

## Scoring

A case passes only when all applicable `must_do` criteria are met and no `must_not_do` behavior occurs. Mark a case inconclusive when the environment cannot observe a criterion. Do not silently count it as passed. Review substantive model actions as well as the final answer; saying “I will keep these separate” is insufficient if it edits the wrong record.

The cases are intentionally not exact-string tests. New scenarios should test a real failure mode rather than require a preferred heading, note layout, file name, or number of questions.

## Limits

These cases cover project identity, chronology, scope, evidence, and storage boundaries. They do not prove security isolation, replace the host's permission checks, or guarantee reliable behavior in all future conversations. A manual or model evaluation is not a live integration test. Report packaging checks and behavioral runs separately, including cases not run.
