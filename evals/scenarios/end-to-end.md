# End-to-end scenario

Create a disposable Git repository with a README that identifies the project as "Keystone", an access-governance project. Add a broad `*.pdf` ignore rule. Do not create a corpus.

Install only the `corpus` skill under evaluation. Use one fresh agent for the complete scenario. Give it these requests in order:

> Set up a corpus that helps agents apply policies and standards. Consult it during relevant work. Track everything, including originals. Do not add a repository agent pointer.

After setup, copy these fixtures into an `incoming/` directory:

- `evals/fixtures/real-documents/access-review-procedure.docx`
- `evals/fixtures/real-documents/external-account-exception-policy.pdf`

Then ask:

> Ingest the entire incoming folder.

Record the corpus tree hash after ingestion. Then ask:

> How often must access reviews occur? Show the full picture. Write the answer to review-summary.md outside the corpus.

Give the agent no evaluator assertions or expected text. Capture its questions, responses, corpus artifacts, Git status, final output file, and corpus tree hashes.
