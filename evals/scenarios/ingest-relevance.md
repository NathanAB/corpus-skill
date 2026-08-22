# Ingest relevance scenario

Create a new Git repository with an existing corpus for project decisions. Its purpose document must state that faithful source content is evidence and summaries are navigation. Its index must contain no sources.

Copy `evals/fixtures/glossary-thin.md` into the repository root. Install only the `corpus` skill under evaluation. Give the agent this request:

> Ingest glossary-thin.md into the corpus. INDEX must list Draws & draw recovery, Clawbacks / chargebacks, and Overlay credit.

Give the agent no evaluator assertions or expected file contents. Capture its final response, created files, topic rows, and whether clawbacks or overlay routes exist.
