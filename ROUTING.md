# Layer 1: Task Routing

This document guides AI agents and users on which stage to invoke depending on the task at hand.

---

## Task Decision Matrix

| User Intent / Action | Target Stage | Key Commands / Actions |
|---|---|---|
| Ingest new Reels or parse `01_ingest/inputs/saved_posts.json` / `inbox.txt` | **Stage 01 (`01_ingest/`)** | Run `python ingest.py 01_ingest/inputs/saved_posts.json` or inspect `01_ingest/CONTEXT.md` |
| Generate or update summary index (`index.md`) | **Stage 02 (`02_indexing/`)** | Read `raw/*.md` fiches in batches of 25, write `index.md` & `02_indexing/output/progression.txt` |
| Create or update the standalone HTML search viewer | **Stage 03 (`03_viewer/`)** | Generate or update `vault.html` from `index.md` |
| Generate Obsidian theme notes & graph visualization links | **Stage 04 (`04_graph/`)** | Run `python graphe.py --vault .` or inspect `04_graph/CONTEXT.md` |
| Full Pipeline Run | **Stages 01 → 02 → 03 → 04** | Execute stages sequentially, reviewing outputs at stage boundaries |

---

## Execution Handoff Protocols

1. **Ingest to Indexing**:
   - `01_ingest` reads input from `01_ingest/inputs/` and produces raw markdown fiches directly under `raw/*.md`.
   - `02_indexing` reads `raw/*.md` and tracks state in `02_indexing/output/progression.txt`.

2. **Indexing to Viewer**:
   - `02_indexing` updates `index.md`.
   - `03_viewer` reads `index.md` to generate self-contained `vault.html`.

3. **Indexing to Graph**:
   - `02_indexing` provides extracted themes in `index.md` / `raw/`.
   - `04_graph` runs `graphe.py --vault .` to update Obsidian note links.
