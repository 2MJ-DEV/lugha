# Lugha

Lugha est un projet collaboratif de creation d'un dataset de traduction pour les langues du Congo, avec un premier focus sur :

- francais (`fra`)
- lingala (`lin`)
- kikongo (`kon`)
- swahili congolais (`swa`)
- tshiluba (`lua`)

L'anglais (`eng`) reste dans le perimetre du projet, mais il n'est pas le pivot initial.

L'objectif est de constituer une base de donnees reutilisable pour :

- des applications de traduction
- des assistants de conversation multilingues
- des systemes de traduction vocale en temps reel
- des futurs modeles IA texte et audio

Le projet est pense en deux couches :

1. un dataset texte de haute qualite
2. un dataset audio aligne sur les phrases du dataset texte

## Structure du depot

```text
data/
  raw/                    # donnees brutes collectees
    languages/            # informations par langue
    translation-pairs/    # contributions texte et audio non nettoyees
  processed/              # donnees nettoyees et normalisees plus tard
    training-ready/       # versions preparees pour entrainement/evaluation
docs/                     # documentation du projet
templates/                # modeles de fichiers a reutiliser
CONTRIBUTING.md           # regles de contribution
```

## Pivot actuel

Pour l'instant, le seul pivot de traduction est le francais (`fra`).

Le flux prioritaire est :

- `fra` -> langue congolaise
- langue congolaise -> `fra`

L'anglais pourra etre ajoute plus tard comme pivot secondaire, une fois que les jeux bases sur le francais seront suffisamment valides et coherents.

## Paires actives

Les paires actives pour la collecte initiale sont :

- `fra-lin`
- `fra-kon`
- `fra-swa`
- `fra-lua`

## Paires futures

Les paires impliquant l'anglais ne sont pas la priorite immediate. Elles peuvent etre ouvertes plus tard, ou en phase secondaire, lorsque les paires avec pivot francais seront jugees suffisamment solides.

Par exemple `fra-lin` peut contenir des traductions francais -> lingala et lingala -> francais, tant que le schema reste explicite.

## Organisation des donnees

Chaque paire de traduction contient :

- `text/` pour les phrases et traductions
- `audio/` pour les voix, les manifests et les metadonnees locuteur

Les fichiers principaux a remplir sont :

- `text/contributions.csv`
- `audio/speakers.csv`
- `audio/manifests/contributions.tsv`

## Cycle de vie des donnees

Le projet distingue desormais deux etapes :

1. `data/raw/` : collecte brute communautaire
2. `data/processed/` : nettoyage, dedoublonnage, normalisation et constitution des jeux d'entrainement

Dans la phase brute :

- les donnees peuvent contenir des doublons
- certaines traductions peuvent etre encore en `draft`
- les variantes regionales peuvent coexister
- l'audio peut etre collecte avant validation finale

Le nettoyage et la preparation des jeux `train`, `validation` et `test` se feront plus tard dans `data/processed/training-ready/`.

## Regles rapides

- une ligne = une unite de sens claire
- pas de donnees sensibles ou personnelles
- pas de contenu haineux, illegal ou dangereux
- toujours indiquer la source et la licence si le texte ne vient pas de vous
- une contribution doit respecter le schema documente dans [docs/dataset-schema.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/docs/dataset-schema.md)
- les nouvelles contributions doivent aller d'abord dans `data/raw/`
- ne pas ouvrir une collecte massive `fra-eng` ou `eng-*` avant validation suffisante du pivot francais

## Documentation

- Guide de contribution : [CONTRIBUTING.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/CONTRIBUTING.md)
- Vision du projet : [docs/project-overview.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/docs/project-overview.md)
- Schema du dataset : [docs/dataset-schema.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/docs/dataset-schema.md)
- Politique de pivot : [docs/pivot-policy.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/docs/pivot-policy.md)
- Exemples de contribution : [docs/contributor-examples.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/docs/contributor-examples.md)
- Standards qualite : [docs/quality-guidelines.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/docs/quality-guidelines.md)

## Demarrage rapide

1. Choisir une langue ou une paire de langues.
2. Lire [CONTRIBUTING.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/CONTRIBUTING.md).
3. Remplir ou etendre les fichiers dans `data/raw/translation-pairs/...`.
4. Si vous contribuez pour la voix, ajouter vos metadonnees dans `audio/speakers.csv` puis vos clips dans `audio/clips/`.
5. Verifier que vos donnees suivent le format attendu.
