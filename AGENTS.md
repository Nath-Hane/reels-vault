# AGENTS.md - Agent Execution Protocol (ICM / Model Workspace Protocol)

This file defines the operational protocol for any AI agent interacting with this repository. It enforces the **Interpretable Context Methodology (ICM / Model Workspace Protocol)** established in [arXiv:2603.16021](https://arxiv.org/abs/2603.16021).

---

## 1. Core Operating Principle

**The filesystem is your orchestrator.** You do not need external multi-agent frameworks or monolithic prompt chains. The workspace is organized into explicit context layers and numbered stage folders. 

At any given moment, **only load the context files required for the current stage** to avoid context window degradation ("lost in the middle").

---

## 2. Context Loading Protocol (5-Layer Hierarchy)

When assigned a task, follow this exact sequence:

1. **Layer 0 - Global Identity**: Read [GLOBAL_IDENTITY.md](file:///c:/Users/nodel/Projects/reels-vault/vault/GLOBAL_IDENTITY.md) to understand workspace conventions and safety boundaries.
2. **Layer 1 - Task Routing**: Consult [ROUTING.md](file:///c:/Users/nodel/Projects/reels-vault/vault/ROUTING.md) to map the user request to the target stage (`01_ingest`, `02_indexing`, `03_viewer`, `04_graph`).
3. **Layer 2 - Stage Contract**: Open the target stage's contract (e.g., [02_indexing/CONTEXT.md](file:///c:/Users/nodel/Projects/reels-vault/vault/02_indexing/CONTEXT.md)) and follow its `Inputs`, `Process`, and `Outputs` sections strictly.
4. **Layer 3 - Scoped Reference Rules**: Load only the reference guidelines specified by the stage contract (e.g., [_config/indexing_rules.md](file:///c:/Users/nodel/Projects/reels-vault/vault/_config/indexing_rules.md)).
5. **Layer 4 - Working Artifacts**: Read the stage input files from `raw/` or previous stage `output/` directories.

---

## 3. Pipeline Stages Summary

| Stage Directory | Stage Contract | Primary Function | Execution Method |
|---|---|---|---|
| `01_ingest/` | [01_ingest/CONTEXT.md](file:///c:/Users/nodel/Projects/reels-vault/vault/01_ingest/CONTEXT.md) | Download Reels & Whisper audio transcription | Run `python ingest.py` |
| `02_indexing/` | [02_indexing/CONTEXT.md](file:///c:/Users/nodel/Projects/reels-vault/vault/02_indexing/CONTEXT.md) | Batch summarization (25 fiches/batch) & theme extraction | Process `raw/*.md` → Append `index.md` |
| `03_viewer/` | [03_viewer/CONTEXT.md](file:///c:/Users/nodel/Projects/reels-vault/vault/03_viewer/CONTEXT.md) | Generate single-file offline HTML viewer | Compile `index.md` → `vault.html` |
| `04_graph/` | [04_graph/CONTEXT.md](file:///c:/Users/nodel/Projects/reels-vault/vault/04_graph/CONTEXT.md) | Generate Obsidian theme notes & wiki-links | Run `python graphe.py` |

---

## 4. Human-in-the-Loop & Review Gates

- **Every output is an edit surface**: After completing a stage, write outputs to the stage's `output/` folder or target file (`index.md`, `vault.html`, `raw/`).
- **Pause for review**: Allow the user to inspect and edit intermediate outputs before executing the next downstream stage.
- **Respect manual edits**: Upstream edits made by the user in `raw/` or `index.md` take priority; downstream stages must read whatever the user left in those files.

---

## 5. Critical Constraints & Rules

1. **Documentation Placement Rule**: Any markdown or documentation files created by agents must be stored in the `.agents/docs/` directory.
2. **Temporary Files Rule**: All temporary scripts, scratch files, or test outputs must be placed in the `tmp/` directory and named with a `tmp` prefix (e.g., `tmp_test_parser.py`).
3. **Use Local Scripts**: For mechanical tasks (video downloading, Whisper transcription, Obsidian graph building), execute the provided Python scripts (`ingest.py`, `graphe.py`) rather than reimplementing them in agent code.
