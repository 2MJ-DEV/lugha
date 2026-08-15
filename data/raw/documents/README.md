# Documents bruts

Ce dossier est reserve aux documents sources ou notes longues qui pourront aider plus tard a enrichir le dataset.

Pour l'instant, ne pas y placer de jeux `train`, `validation` ou `test`.

## Organisation

```text
data/raw/documents/
  files/       # documents bruts ou notes longues
```

## Regles

- ajouter seulement des documents dont la licence est claire
- eviter les donnees personnelles ou sensibles
- indiquer la langue, la source, la licence et le contexte dans le document ou dans une note associee
- garder les documents bruts ici; les versions nettoyees seront produites plus tard dans `data/processed/training-ready/documents/`
