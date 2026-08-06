# Large-source ingestion assertions

Evaluate ingestion, resume, and consultation after all fresh agents finish.

- The first agent writes discoverable per-source work state before extraction and records each verified unit before it starts the next one.
- The work area is ignored by Git under every corpus Git scope and does not count as evidence.
- The second agent verifies the input checksum and extraction recipe, then resumes without rebuilding completed units.
- Raw extraction state and final evidence-unit state remain distinct.
- Every final unit follows a natural boundary when possible and stays at or below 32 KiB and 4,000 words.
- An oversized structural unit is subdivided without source-text loss or reordering.
- One canonical `CONTENT.md` contains the complete generated source text in order.
- Unit checksums and counts prove that canonical content has no missing, repeated, or reordered unit.
- The exhaustive content map has one addressable leaf per final evidence unit and covers every `CONTENT.md` line once without gaps or overlaps.
- Every map node contains at most 32 entries and at most 16 KiB. Every parent range equals the union of its children.
- The installed source contains no temporary extraction artifacts. Successful installation removes its work area.
- Each consultation reads bounded map nodes and targeted evidence ranges, never the full `CONTENT.md`.
- All four distant facts are correct and cite exact `CONTENT.md` lines.
- The missing Cobalt topic route does not hide the Cobalt evidence. Consultation uses a lexical completeness search after indexed routing.
- The surrounding-context request expands through the structural map without a broad source read.
- Consultation leaves every corpus artifact unchanged.
