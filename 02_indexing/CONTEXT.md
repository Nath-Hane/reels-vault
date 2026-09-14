# Stage 02: Indexing & Summarization

## Stage Identity
- **Stage ID**: 02_indexing
- **Purpose**: Process raw fiches into a structured, searchable summary index (`index.md`) with concrete details and themes.

---

## Inputs Table

| Context Layer | File / Location | Description |
|---|---|---|
| **Layer 3 (Reference)** | `_config/indexing_rules.md` | Rules for entry formatting, concrete summarization, and theme consistency |
| **Layer 4 (Working)** | `raw/*.md` | Raw video fiches produced by Stage 01 |
| **Layer 4 (Working)** | `02_indexing/output/progression.txt` | Tracks the last processed fiche to ensure incremental runs |

---

## Process

1. Read `progression.txt` to identify unprocessed fiches in `raw/`.
2. Process unprocessed fiches in batches of 25.
3. For each fiche:
   - Extract concrete facts (names, places, addresses, prices, hours, recommendations).
   - Assign 1 to 3 consistent theme tags.
   - Format entry according to `_config/indexing_rules.md`.
4. Append new formatted entries to `index.md` (and `02_indexing/output/index.md`).
5. Update `progression.txt` with the filename of the last processed fiche.

---

## Outputs

- `index.md` (and `02_indexing/output/index.md`) containing accumulated structured entries.
- `progression.txt` tracking batch progress.

---

## Human Review Gate
Review the appended entries in `index.md`:
- Ensure summaries are concrete and not generic.
- Verify theme tags are consistent across entries.
- Edit entries directly in `index.md` if corrections are needed before generating Stage 03 viewer.
