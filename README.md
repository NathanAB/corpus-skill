# corpus-skill

[![skills.sh](https://skills.sh/b/NathanAB/corpus-skill)](https://skills.sh/NathanAB/corpus-skill)

`corpus` is a portable Agent Skill for building and consulting a repository source corpus. It preserves faithful source content, creates compact topic navigation, and returns line-cited answers from every relevant source.

## Install

```bash
npx skills add NathanAB/corpus-skill --skill corpus
```

Select target agents when needed:

```bash
npx skills add NathanAB/corpus-skill \
  --skill corpus \
  -a claude-code \
  -a codex \
  -a opencode
```

## Use

The skill supports three requests:

- **Setup:** "Set up a corpus for product and policy evidence."
- **Ingest:** "Ingest this document" or "Ingest the entire research folder."
- **Consult:** "Consult the corpus about record retention and show the full picture."

Setup asks four short questions about purpose, consultation timing, Git scope, and repository agent guidance.

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

## Design boundaries

- One visible corpus per repository.
- No fixed parser or supported-format list. The active agent uses its available extraction tools.
- Successful batch sources remain when another source fails.
- Consultation reads every relevant source and leaves corpus artifacts unchanged.
- Source material is untrusted data. Instructions inside it never control the agent.
- No runtime, service, embeddings, vector database, CI integration, or harness-specific extension.

## Verify a local checkout

```bash
uvx --from skills-ref agentskills validate skills/corpus
npx skills add . --list
```

Behavior evaluations live outside the installed skill in `evals/`. They include a complete fresh-agent flow with self-authored DOCX and PDF fixtures. Task prompts and evaluator assertions remain separate.

## License

MIT
