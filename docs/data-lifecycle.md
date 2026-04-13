# Cycle de vie des donnees

## Vue simple

Le projet suit ce chemin :

1. collecte brute
2. relecture communautaire
3. nettoyage et dedoublonnage
4. normalisation
5. creation des jeux pour entrainement et evaluation

Au stade actuel, cette collecte brute est orientee d'abord autour du pivot francais.

## Dossiers

### `data/raw/`

Contient les contributions telles qu'elles arrivent depuis la communaute.

On y accepte :

- doublons potentiels
- traductions en cours de validation
- variantes regionales documentees
- audio avec statut non final

### `data/processed/`

Contient les donnees derivees a partir du brut.

On y place plus tard :

- jeux `train`, `validation`, `test`
- sous-ensembles filtres
- donnees normalisees
- manifests audio verifies

## Regle de gouvernance

On ne modifie pas manuellement `data/processed/` pour y ajouter des contributions brutes. Toute nouvelle contribution commence dans `data/raw/`.
