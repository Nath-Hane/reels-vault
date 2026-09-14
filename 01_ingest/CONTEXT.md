# Stage 01: Ingestion & Transcription

## Stage Identity
- **Stage ID**: 01_ingest
- **Purpose**: Fetch Reels metadata, download audio, perform local Whisper transcription, and generate raw markdown fiches.

---

## Inputs Table

| Context Layer | File / Location | Description |
|---|---|---|
| **Layer 3 (Reference)** | `GLOBAL_IDENTITY.md` | Workspace identity and rules |
| **Layer 4 (Working)** | `01_ingest/inputs/saved_posts.json` / `saved_collections.json` / `inbox.txt` | Source Instagram/TikTok links to process |
| **Script Tool** | `ingest.py` | Python execution engine (`yt-dlp` + `faster-whisper` + `gallery-dl`) |

---

## Process

1. Execute `ingest.py` specifying the source file from `01_ingest/inputs/` (or `inbox.txt`).
2. Extract video description, author metadata, and audio stream.
3. Transcribe audio using Whisper model locally.
4. Extract frame snapshots if audio is silent/insufficient.
5. Write raw markdown fiches to `raw/`.
6. Update execution journal (`01_ingest/output/journal.json`).

```bash
python ingest.py "01_ingest/inputs/saved_posts.json" --vault . --cookies firefox --limite 10
```

---

## Outputs

- Raw markdown video fiches saved directly under `raw/*.md`.
- `01_ingest/output/journal.json` tracking processed URLs.
- Extracted image assets saved in `images/`.

---

## Human Review Gate
Check newly created fiches in `raw/`:
- Verify that transcription section contains meaningful content.
- If audio transcription is empty, flag fiche for image reading or manual note addition before Stage 02.
