# Setup

Create one repository corpus through a short guided process.

## 1. Inspect

1. Locate the repository root.
2. If `corpus/` exists, stop and report that the repository already has its one corpus.
3. Inspect top-level documentation, project manifests, and repository-wide agent instruction files.
4. Infer a short corpus title from repository context. Do not ask for facts that the repository provides.

Complete this step when you know the repository purpose, likely corpus title, and available agent instruction file.

## 2. Resolve policies

Fill each policy from the request first. Do not re-ask a choice the request already made.

When the request is silent, apply these defaults instead of asking:

1. **Purpose** — Infer from repository context. Use the nearest of: answer domain or product questions; ground project decisions; compare research or competing sources; apply policies or standards. Write a one-sentence purpose. Ask only when the repository does not support an inference.
2. **When to consult** — During relevant work.
3. **Agent pointer** — Yes. Add the recommended short pointer.

**Git scope has no default.** If the request does not choose one, ask only this question. Use structured multiple-choice input when available. Otherwise present one compact numbered form:

- Navigation only: purpose, index, summaries, and provenance. Clones cannot consult; `CONTENT.md` is not in Git.
- Navigation and readable content: keep originals local. Clones can consult `CONTENT.md`.
- Everything: include originals. Clones can consult and also receive the source files.
- Custom

Ask one short follow-up only when a custom Git choice lacks required detail. Do not ask purpose, consult timing, or pointer unless they are still unresolved after inference and defaults.

Complete this step when every answer maps to a concrete purpose, consultation policy, Git policy, and pointer choice. If Git scope is still unresolved, stop after that question. Do not create corpus files yet.

## 3. Create

1. Create `corpus/sources/` with an empty `.gitkeep` file so Git can preserve the source container.
2. Create `corpus/CORPUS.md` from [the corpus template](../assets/CORPUS.template.md).
3. Create `corpus/INDEX.md` from [the index template](../assets/INDEX.template.md). Keep it free of topic entries until ingestion.
4. Replace every placeholder with repository facts and user choices.
5. Record the selected Git scope in `CORPUS.md` by name and say whether clones can consult `CONTENT.md`.

Write the files immediately after the answers. Do not show a preview or ask for final confirmation.

## 4. Apply the Git policy

- **Navigation only:** ignore every `CONTENT.md`, `original`, and `original.*` below `corpus/sources/`.
- **Navigation and readable content:** ignore every `original` and `original.*` below `corpus/sources/`.
- **Everything:** track every installed source artifact.
- **Custom:** add only the ignore rules required by the user's artifact choices.

Always ignore `corpus/.work/`. It contains resumable process state, not corpus evidence.

Preserve all unrelated rules. Add one short labeled block at the end of `.gitignore`. Start it with `!corpus/` and `!corpus/**` so earlier rules cannot hide selected artifacts. Put `corpus/.work/` and the selected source exclusions after those negation patterns.

Use `git check-ignore --no-index` to verify created artifacts against the selected scope. Never stage or commit files.

## 5. Add agent guidance

If the user selected the pointer, adapt [the agent instruction template](../assets/agent-instruction.template.md) and add it to the repository-wide agent instruction file. If none exists, create `AGENTS.md`.

Keep the pointer short. State when agents consult the corpus and that they start with `corpus/CORPUS.md` and `corpus/INDEX.md`.

## 6. Check integrity

Before reporting success, verify all of these conditions:

- `corpus/CORPUS.md`, `corpus/INDEX.md`, `corpus/sources/`, and `corpus/sources/.gitkeep` exist.
- No template placeholder remains.
- `corpus/INDEX.md` contains no topic entry.
- The ignore rules match the selected Git policy.
- Git ignores `corpus/.work/` under every Git policy.
- Git reports every artifact selected for Git as trackable.
- The agent pointer exists when selected.
- No corpus file is staged or committed by this workflow.

Fix a failed condition before reporting success. Report the created files, selected policies, and any repository instruction change.
