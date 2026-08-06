# Batch ingestion scenario

Create a new Git repository with a configured corpus. Use the skill to ingest `architecture-memo.md` from the fixture directory as its existing source.

Create an incoming tree with:

- an exact byte copy of the existing architecture memo;
- a nested changed copy named `architecture-memo.md` from `architecture-memo-revised.md`;
- a nested `decision-review.md`;
- a hidden source, a temporary source, and an obvious generated lock file.

Install only the `corpus` skill under evaluation. Give the agent this request:

> Ingest the entire incoming folder and missing-source.md. Keep successful results if anything fails. Supersede the existing architecture memo with the changed copy.

Give the agent no evaluator assertions or expected file contents. Capture its final response, created files, index, source relationships, and a second run of the same request.
