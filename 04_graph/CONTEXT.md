# Stage 04: Obsidian Graph Generation

## Stage Identity
- **Stage ID**: 04_graph
- **Purpose**: Transform raw fiches and index themes into an interconnected Obsidian markdown vault graph.

---

## Inputs Table

| Context Layer | File / Location | Description |
|---|---|---|
| **Layer 4 (Working)** | `raw/*.md` | Raw video fiches |
| **Script Tool** | `graphe.py` | Python graph generation script |

---

## Process

1. Run `graphe.py` targeting the vault root:
   ```bash
   python graphe.py --vault .
   ```
2. `graphe.py` parses theme tags across all fiches.
3. Inserts Obsidian wiki-links (`[[Thème]]`) into each video fiche.
4. Generates theme notes under `synced/` / `themes/` (or `04_graph/output/`).

---

## Outputs

- Updated fiches with `[[Thème]]` links.
- Generated theme notes for Obsidian graph view.

---

## Human Review Gate
Open Obsidian vault:
- Press `Ctrl+G` to open Graph View.
- Adjust force parameters (Repel) and color groups to inspect node relationships.
