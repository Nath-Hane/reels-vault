# Documentation : Protocole d'Exécution des Agents (`AGENTS.md`)

Ce document est la copie archivée dans `.agents/docs/` des directives d'exécution des agents IA opérant sur le workspace **Reels Vault**, en accord avec l'architecture **ICM (Interpretable Context Methodology - arXiv:2603.16021)**.

---

## Principes Directeurs
1. **Orchestration par le Système de Fichiers** : Aucune dépendance à un framework d'agent complexe. La structure des dossiers et les contrats d'étapes (`CONTEXT.md`) régissent l'exécution.
2. **Chargement de Contexte Séparé (5 Layers)** :
   - Layer 0 : `GLOBAL_IDENTITY.md`
   - Layer 1 : `ROUTING.md`
   - Layer 2 : `0X_stage/CONTEXT.md`
   - Layer 3 : `_config/indexing_rules.md`
   - Layer 4 : `raw/` et fichiers `output/`
3. **Portes de Révision Humaine (Review Gates)** : Chaque sortie d'étape est révisable et modifiable par l'utilisateur avant le lancement de l'étape suivante.
4. **Utilisation des Scripts Locaux** : Les tâches lourdes et déterministes sont déléguées aux scripts Python du dépôt (`ingest.py`, `graphe.py`).
5. **Règles du Dépôt** :
   - Toute documentation créée par un agent doit résider dans `.agents/docs/`.
   - Tout fichier temporaire doit être placé dans `tmp/` et commencer par `tmp`.
