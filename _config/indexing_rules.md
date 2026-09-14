# Layer 3: Indexing Rules & Guidelines

Ce fichier contient les règles de référence permanentes pour la transformation des fiches brutes en entrées d'index.

---

## 1. Principes de Résumé (Stage 02)
- **Concret et factuel** : Extraire uniquement les noms propres, adresses, prix, horaires, conseils spécifiques et recommandations mentionnés dans la transcription audio ou la description.
- **Interdiction des généralités** : Ne jamais écrire de phrase floue du type "cette vidéo parle de productivité" ou "conseils pour voyager".
- **Fiches pauvres** : Si une fiche ne contient aucune information exploitable (musique seule, texte flou), indiquer explicitement qu'elle est "incomplète/non résumable" plutôt qu'inventer du contenu.

---

## 2. Format des Entrées (`index.md`)

Chaque entrée ajoutée à `index.md` doit respecter strictement ce format Markdown :

```markdown
### <titre court et explicite>
- lien : <url>
- auteur : <auteur>
- thèmes : <thème1>, <thème2>
- contenu : <résumé concret de 2 à 4 lignes avec noms, lieux, prix, adresses>
```

---

## 3. Gestion des Thèmes
- Attribuer 1 à 3 thèmes par vidéo.
- **Réutilisation des libellés** : Utiliser un vocabulaire cohérent d'une fiche à l'autre (ex: `Restaurant`, `Japon`, `Productivité`, `Paris`, `Patisserie`).
- Ne pas prédéfinir une liste rigide : déduire les thèmes du contenu réel.

---

## 4. Traitement par Lots
- Traiter les fiches brutes de `raw/` par lots de 25.
- Conserver le nom du dernier fichier traité dans `progression.txt` pour permettre des relances incrémentales sans re-traiter les fichiers déjà indexés.
