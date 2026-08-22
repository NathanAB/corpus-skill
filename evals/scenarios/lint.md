# Lint scenario

Create a new Git repository with an existing corpus for project decisions. Install only the `corpus` skill under evaluation. Ingest `evals/fixtures/glossary-thin.md`.

Then plant a false route without changing `CONTENT.md`: add a Clawbacks / chargebacks topic on both `SOURCE.md` and `INDEX.md` that cites the Alignment lines.

Record the corpus tree hash, then ask:

> Lint the corpus navigation. Report false topic routes.

Record whether any corpus file changed. Then ask:

> Repair the navigation findings from that lint.

Capture the lint report, both tree hashes, and whether `CONTENT.md` changed.
