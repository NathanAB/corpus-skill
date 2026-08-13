---
name: corpus
description: Use when creating a git-tracked evidence corpus, ingesting markdown, PDF, or Word files, or answering from those sources with citations. Use when the user wants agents to cite policy, handbook, or source-of-truth documents instead of paraphrasing them, or when corpus/ already exists. Do not use for generic RAG, wikis, chat memory, or a one-off file to read once.
license: MIT
---

# Corpus

Maintain one visible evidence corpus in `corpus/`. Cite `CONTENT.md`. This is not RAG, a wiki, or chat memory.

## Setup

For corpus creation, initialization, setup, or bootstrap, read [the setup workflow](references/setup.md) completely and follow it.

## Ingest

For any source addition, import, ingestion, conversion, or indexing request, read [the ingestion workflow](references/ingest.md) completely and follow it.

## Consult

For any question, research, comparison, or verification request against an existing corpus, read [the consultation workflow](references/consult.md) completely and follow it.

Use the bundled templates as starting structures. Adapt their content to the user's answers and repository context. Leave no template placeholders in created files.
