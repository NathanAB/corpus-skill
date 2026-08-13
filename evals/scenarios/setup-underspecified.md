# Underspecified setup scenario

Create a new Git repository with:

- a README that identifies the project as "Northstar", a tool for architecture decisions;
- an `AGENTS.md` file with a general repository instruction;
- no existing corpus.

Install only the `corpus` skill under evaluation. Give the agent this request:

> Set up a corpus.

Give the agent no evaluator assertions, policy answers, or expected file contents. Capture its questions, final response, created files, Git diff, and staged-file state.
