# Corpus

[![skills.sh](https://skills.sh/b/NathanAB/corpus-skill)](https://skills.sh/NathanAB/corpus-skill)

A skill that keeps source documents as a git-tracked **evidence** folder your agent cites by file and line. It is not a search index, not a wiki, and not a file converter.

Install it, copy the example, and ask one consult question. You should get an answer that quotes the real text, including conflicts.

<img width="220" height="263" alt="learning" src="https://github.com/user-attachments/assets/82ce380c-12c3-4719-b6ef-e6290b65daa0" />

_Above: your agent invoking corpus_

Version: [`0.2.0`](skills/corpus/VERSION)

## Install

```bash
npx skills add NathanAB/corpus-skill
```

## Try it

From a git repo where the skill is installed:

```bash
cp -R path/to/corpus-skill/examples/retention corpus
```

If this repository is already the working copy:

```bash
cp -R examples/retention corpus
```

Then ask:

> Consult the corpus about record retention. Show the full picture.

You should see both the seven-year and ten-year positions, with citations into `corpus/sources/*/CONTENT.md`. The example also contains an embedded instruction to ignore citation rules; a correct consult treats that as untrusted text and does not follow it.

## Use

- **Setup:** one-time bootstrap in a project that has no corpus yet.
  > Set up a corpus for product and policy evidence
- **Ingest:** add source files or folders.
  > Ingest notes/retention-policy.md into the corpus
- **Consult:** answer from ingested evidence.
  > Consult the corpus about record retention. Show the full picture.

## Limits

- Scanned or image-only PDFs fail. There is no OCR path in this skill.
- Word, PowerPoint, and text PDFs are converted with whatever tools the agent already has. Corpus stores the result as evidence; it does not ship a converter.
- Already-readable markdown and text copy through as-is.
- Claims must come from `CONTENT.md`, not from summaries or the topic index.

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
