# Layer 0: Global Workspace Identity

## Workspace Overview
- **Name**: Reels Vault
- **Architecture**: Interpretable Context Methodology (ICM / Model Workspace Protocol - arXiv:2603.16021)
- **Purpose**: Transform saved Instagram Reels and TikTok videos into an offline-first, searchable, and graphable structured database.

## System Boundaries & Principles
1. **Filesystem as Orchestrator**: Folder structure and stage contracts (`CONTEXT.md`) govern pipeline execution.
2. **Explicit Layered Context Loading**:
   - **Layer 0**: `GLOBAL_IDENTITY.md` (Global guidelines & architecture overview)
   - **Layer 1**: `ROUTING.md` (Task router mapping user intent to stages)
   - **Layer 2**: `0X_stage/CONTEXT.md` (Stage-specific input/process/output contract)
   - **Layer 3**: `_config/` and `references/` (Factory configuration, rules, guidelines)
   - **Layer 4**: `raw/` and `stage/output/` (Run-specific working artifacts)
3. **Plain Text Interface**: Every intermediate output is a readable file (Markdown/JSON/HTML).
4. **Local Execution**: Heavy non-AI operations (video fetching, audio extraction, Whisper transcription) are handled by local Python scripts (`ingest.py`, `graphe.py`).
5. **Documentation Rule**: All agent-created documentation is stored in `.agents/docs/`. All temporary files go into `tmp/` with prefix `tmp`.

## Workspace Structure
- `01_ingest/` : Ingestion & transcription pipeline stage.
- `02_indexing/` : Batch summarization & indexing stage.
- `03_viewer/` : Interactive offline HTML viewer generation stage.
- `04_graph/` : Obsidian graph links & theme note generation stage.
- `_config/` : System configuration rules.
- `.agents/docs/` : Workspace architectural & operational documentation.
