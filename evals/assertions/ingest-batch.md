# Batch ingestion assertions

Evaluate both batch runs after the agent finishes.

- Subfolders are traversed.
- Hidden, temporary, and generated files are skipped and reported.
- The exact architecture-memo copy is skipped through byte identity.
- The changed architecture memo becomes a new source record that supersedes the older record.
- Both source cards describe the supersession relationship.
- Decision review succeeds even though the named missing source fails.
- The failure has a clear reason and removes no successful result.
- The failure leaves no broken source record or index route.
- The first report separates successes, duplicate skips, ignored files, conflicts, and failures.
- The second run skips exact successes and retries the missing input without a separate state file.
- The topic index contains every relevant source and exact content ranges.
- Every successful source has complete content-map coverage and no remaining work state.
