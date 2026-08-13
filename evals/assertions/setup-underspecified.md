# Underspecified setup assertions

Evaluate the underspecified setup scenario after the agent finishes its first turn.

- The corpus title is inferred from the Northstar repository context.
- The corpus purpose is inferred as grounding project or architecture decisions. The agent does not ask what the corpus is for.
- The agent does not ask when to consult. Consultation policy is during relevant work.
- The agent does not ask whether to add a repository pointer. The pointer is yes.
- The agent asks what belongs in Git, using the setup Git-scope choices. Each choice states whether a clone can consult `CONTENT.md`.
- The agent does not ask any other setup question.
- If the agent created corpus files on this turn, Git scope is still unresolved in those files or the run failed closed. Do not accept a silent Git-scope default.
