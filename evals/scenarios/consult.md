# Consultation scenario

Create a new Git repository with a configured corpus. Use the skill to ingest `retention-policy.md`, `regulatory-retention-opinion.md`, and `retention-survey.md` from the fixture directory.

Install only the `corpus` skill under evaluation. Record the corpus tree hash, then ask:

> How long must audit records be retained? Show the full picture.

Next, remove all topic entries from the index without changing source cards or content. Record the new corpus tree hash, then ask:

> What happens to scheduled deletion during litigation?

Finally ask:

> Does this corpus specify an encryption-key rotation interval?

Give the agent no evaluator assertions or expected answer. Capture all answers, citations, index-miss disclosure, file changes, and corpus tree hashes before and after each consultation.
