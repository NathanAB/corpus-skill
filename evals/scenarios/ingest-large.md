# Large-source ingestion scenario

Create a disposable Git repository with a configured corpus. Generate one plain-text operations manual with 96 numbered chapters and at least 100,000 words. Give every chapter a unique title and one unique fact. Include these facts in distant chapters:

- Chapter 4: Amber records expire after 17 days.
- Chapter 37: Cobalt reviews occur every 42 days.
- Chapter 71: Juniper access requires two custodians.
- Chapter 96: Quartz exports stop during a legal hold.

Install only the `corpus` skill under evaluation. Give a fresh agent this request:

> Ingest the generated operations manual.

Stop the agent after several extraction units succeed but before source installation. Capture the work-state tree and start a fresh agent with the same request. Capture its tool reads, work-state changes, installed source, maps, checksums, and final response.

Then remove the Cobalt route from the corpus topic index without changing source maps or content. Use another fresh agent for these requests:

> Consult the corpus about Amber record expiration, Cobalt review timing, Juniper access, and Quartz legal holds. Show the full picture.

> What does the surrounding section say before and after the Cobalt review rule?

Give the agents no evaluator assertions, unit limits, expected routes, or expected answers.
