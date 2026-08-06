
# Corpus

[![skills.sh](https://skills.sh/b/NathanAB/corpus-skill)](https://skills.sh/NathanAB/corpus-skill)

`corpus` is a skill for creating and maintaining a permanent knowledge base for your agents. Simply bootstrap the corpus, then point the agent to any source materials or documents you want the corpus to ingest. These documents will be permanently indexed and added to your project corpus and can be consulted at any point in the future by your agents.

<img width="220" height="263" alt="learning" src="https://github.com/user-attachments/assets/82ce380c-12c3-4719-b6ef-e6290b65daa0" />

_Above: your agent invoking corpus_

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
└── sources/
    ├── .gitkeep
    └── <source-id>/
        ├── SOURCE.md
        ├── CONTENT.md
        └── original or original.*
```

- `CORPUS.md` records purpose, policies, Git scope, and agent guidance.
- `INDEX.md` maps topics to every relevant source and exact content range.
- `SOURCE.md` records provenance, navigation summaries, topics, relationships, and extraction warnings.
- `CONTENT.md` is the faithful agent-readable evidence.
- `original` or `original.*` is the unchanged source copy.

Summaries and index entries guide discovery. Claims cite `CONTENT.md`, with original page or section details when available.

## License

MIT
