# Single-source ingestion scenario

Create a new Git repository with an existing corpus for project decisions. Its purpose document must state that faithful source content is evidence and summaries are navigation. Its index must contain no sources.

Copy `evals/fixtures/architecture-memo.md` into the repository root. Install only the `corpus` skill under evaluation. Give the agent this request:

> Ingest architecture-memo.md into the corpus.

Give the agent no evaluator assertions or expected file contents. Capture its final response, created files, Git status, and readable-content line numbers.
