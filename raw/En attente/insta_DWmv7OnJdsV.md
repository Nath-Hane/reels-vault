---
source: https://www.instagram.com/reel/DWmv7OnJdsV/
plateforme: Instagram
genre: video
auteur: Bashiri Smith
duree_s: 5.572000026702881
traite_le: 2026-09-08
statut: brut
---

# Video by bashi_fuirkashi

## Description
When someone says “RAG over millions of PDFs”
they’re not asking about AI…

they’re asking about search + systems.

Here’s what that actually looks like 👇

I’d break it into 5 parts: ingestion, embeddings, retrieval, generation, monitoring

1️⃣ Ingestion is offline, not request-time
At scale, this must be async

• Stream documents from storage (S3/GCS)
• OCR only when needed
• Clean + normalize text
• Chunk intelligently (not randomly)
• Attach rich metadata (doc, page, section, etc.)

None of this should ever touch your user request path

2️⃣ Embeddings + indexing built for scale
You don’t embed on demand

• Batch embedding jobs (GPU or queued)
• Distributed ANN indexes (Milvus, Qdrant, Vespa, Elastic)
• Sharding + HNSW / IVF / PQ
• Store metadata alongside vectors

Key insight:
metadata filtering is your first gate
vector search is the fallback

3️⃣ Retrieval + generation (tight path)
Your request path should stay minimal:

query → metadata filter → cache → ANN search → rerank → LLM

• Most queries never even hit vector search
• Many don’t hit the DB at all (cache wins)
• Rerank a small set only
• Send 5–10 chunks max to the LLM

More context ≠ better results
More chunks usually hurt

4️⃣ Caching is everything
This is what controls cost + latency

• Query → answer cache (FAQs, repeats)
• Query → retrieval cache (top chunks)
• Data/index cache (hot vectors, parsed docs)

Real path looks like:

query → cache → (miss) retrieve + LLM → write back

5️⃣ Monitoring closes the loop
Without this, your system silently degrades

• Retrieval quality (recall@k)
• Answer quality (feedback loops)
• Latency + cache hit rates
• Re-embed + re-shard as data evolves

BOTTOM LINE:

RAG at scale is NOT an LLM problem
It’s a search + caching architecture problem

Most people are building demos
Real AI engineers are building systems

Comment “RAG” and I’ll send you a full breakdown 👇

## Transcription audio
(pas d'audio exploitable)

## Images
- images/insta_DWmv7OnJdsV_1.jpg
- images/insta_DWmv7OnJdsV_2.jpg
- images/insta_DWmv7OnJdsV_3.jpg
