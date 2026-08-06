
# Corpus

[![skills.sh](https://skills.sh/b/NathanAB/corpus-skill)](https://skills.sh/NathanAB/corpus-skill)

`corpus` is a skill for creating and maintaining a permanent knowledge base for your agents. Simply bootstrap the corpus, then point the agent to any source materials or documents you want the corpus to ingest. These documents will be permanently indexed and added to your project corpus and can be consulted at any point in the future by your agents.

<img width="220" height="263" alt="learning" src="https://github.com/user-attachments/assets/82ce380c-12c3-4719-b6ef-e6290b65daa0" />

_Above: your agent invoking corpus_

Version: [`0.2.0`](skills/corpus/VERSION)

## Install

```bash
npx skills add NathanAB/corpus-skill
```

## Use

Corpus is used in three ways

- **Setup:** A one-time setup to bootstrap the corpus.
  > "Set up a /corpus for product and policy evidence"
- **Ingest:** Adding one or more new source materials to the corpus.
  > "Ingest the entire research folder into the /corpus"
- **Consult:**
  > "Consult the /corpus about record retention and show the full picture."

## Corpus structure

```text
corpus/
├── CORPUS.md
├── INDEX.md
├── .work/                         # ignored, present only during ingestion
└── sources/
    ├── .gitkeep
    └── <source-id>/
        ├── SOURCE.md
        ├── CONTENT.md
        ├── map/                   # present when source navigation is large
        └── original or original.*
```

- `CORPUS.md` records purpose, policies, Git scope, and agent guidance.
- `INDEX.md` maps topics to every relevant source and the smallest useful navigation route.
- `SOURCE.md` records provenance, navigation summaries, an exhaustive content map, topics, relationships, and extraction warnings.
- `CONTENT.md` is the faithful agent-readable evidence.
- `map/` holds bounded source-map nodes when the complete map does not fit in `SOURCE.md`.
- `original` or `original.*` is the unchanged source copy.
- `.work/` holds ignored resumable process state. Successful ingestion removes it.

Summaries and index entries guide discovery. Claims cite `CONTENT.md`, with original page or section details when available.

## Large sources

Ingestion keeps large documents out of agent context. It extracts directly to disk, resumes interrupted work, and builds one canonical `CONTENT.md` from bounded evidence units.

Each evidence unit follows natural source boundaries and stays within both limits:

- 32 KiB;
- 4,000 words.

An exhaustive content map gives every evidence unit its own leaf. Map nodes contain at most 32 entries and 16 KiB. Consultation descends through those nodes, reads exact evidence ranges, and runs a bounded text search to catch incomplete topic routes.

## License

MIT
