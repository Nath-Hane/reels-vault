# ICM Architecture Documentation (Reels Vault)

Ce document décrit l'architecture **Interpretable Context Methodology (ICM / Model Workspace Protocol)** mise en place dans ce dépôt, conformément aux principes de l'article [arXiv:2603.16021](https://arxiv.org/abs/2603.16021).

---

## Vue d'ensemble

L'architecture ICM remplace les frameworks d'orchestration multi-agents complexes par une structure de dossiers et de fichiers Markdown explicites. Le système s'articule autour de 5 niveaux de contexte et d'un pipeline séquentiel d'étapes.

---

## Niveaux de Contexte (Context Hierarchy)

1. **Layer 0 - Global Identity (`GLOBAL_IDENTITY.md`)** :
   Définit l'identité du workspace, sa structure globale et les règles fondamentales régissant les agents et les scripts.
2. **Layer 1 - Task Routing (`ROUTING.md`)** :
   Guide de routage orientant l'agent vers les bonnes étapes selon l'intention de l'utilisateur (ingérer des vidéos, mettre à jour l'index, générer le viewer HTML, construire le graphe).
3. **Layer 2 - Stage Contracts (`0X_stage/CONTEXT.md`)** :
   Contrats explicites décrivant les entrées (`Inputs`), le traitement (`Process`) et les sorties (`Outputs`) de chaque étape.
4. **Layer 3 - Reference & Config Material (`_config/`, `references/`)** :
   Règles métier, conventions de formatage, schémas de données et règles d'indexation persistants d'un lancement à l'autre.
5. **Layer 4 - Working Artifacts (`raw/`, `output/`)** :
   Fichiers d'entrée/sortie dynamiques générés à chaque exécution du pipeline.

---

## Découpage des Étapes (Pipeline)

Le pipeline d'indexation et d'analyse des Reels Instagram est découpé en 4 étapes séquentielles :

```
vault/
├── GLOBAL_IDENTITY.md
├── ROUTING.md
├── _config/
│   └── indexing_rules.md
├── 01_ingest/
│   ├── CONTEXT.md
│   └── output/
├── 02_indexing/
│   ├── CONTEXT.md
│   └── output/
├── 03_viewer/
│   ├── CONTEXT.md
│   └── output/
└── 04_graph/
    ├── CONTEXT.md
    └── output/
```

- **Stage 01 (`01_ingest/`)** : Téléchargement des médias, extraction audio & transcription local avec Whisper via `ingest.py`. Sortie : Fiches Markdown brutes dans `raw/` ou `01_ingest/output/`.
- **Stage 02 (`02_indexing/`)** : Analyse par lots (25 fiches), extraction des thèmes et synthèse concrète. Sortie : `index.md` & `progression.txt`.
- **Stage 03 (`03_viewer/`)** : Génération ou mise à jour du moteur de recherche autonome hors-ligne `vault.html`.
- **Stage 04 (`04_graph/`)** : Génération des liaisons thématiques pour Obsidian via `graphe.py`. Sortie : `themes/` et graphe Obsidian.
