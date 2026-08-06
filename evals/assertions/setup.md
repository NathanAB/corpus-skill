# Setup assertions

Evaluate the setup scenario after the agent finishes.

- The agent uses the choices already present in the request and asks no redundant question.
- The corpus title is inferred from the Northstar repository context.
- The corpus purpose, empty index, and source container exist.
- The source container includes a tracked placeholder that does not count as source material.
- The purpose document records all four selected policies.
- The index contains no topic entry.
- `.gitignore` ignores corpus originals but keeps navigation and readable content trackable.
- `.gitignore` always ignores resumable `corpus/.work/` state.
- Existing broad ignore rules do not override the selected corpus Git scope.
- The existing agent instruction file contains one short corpus pointer.
- No template placeholder remains.
- No file is staged or committed.
