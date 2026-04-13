# Backlog initial

Ce document propose 5 premiers issues pouvant etre travailles en parallele avec un risque minimal de conflit.

Principe de decoupage :

- 1 issue = 1 zone de fichiers clairement delimitee
- aucun ticket ne modifie `README.md`, `CONTRIBUTING.md`, `templates/` ou `docs/dataset-schema.md`
- chaque ticket reste dans son propre sous-dossier

## Issue 1 - Completer le premier lot `fra-lin`

**Objectif**

Ajouter un premier lot coherent de donnees texte et audio pour la paire `fra-lin`.

**Fichiers autorises**

- `data/raw/translation-pairs/fra-lin/text/contributions.csv`
- `data/raw/translation-pairs/fra-lin/audio/speakers.csv`
- `data/raw/translation-pairs/fra-lin/audio/manifests/contributions.tsv`
- fichiers audio sous `data/raw/translation-pairs/fra-lin/audio/clips/`

**Travail attendu**

- ajouter au moins 25 nouvelles paires de phrases utiles
- ajouter les locuteurs necessaires dans `speakers.csv`
- ajouter au moins 10 enregistrements audio relies a des `example_id` existants
- respecter les statuts `draft`, `reviewed` ou `validated`

**Criteres d'acceptation**

- aucun `example_id` duplique
- les colonnes existantes ne changent pas
- chaque entree audio pointe vers une phrase existante
- les chemins declares dans le manifest correspondent a des fichiers reels

**Ne pas toucher**

- tout autre dossier que `fra-lin`

## Issue 2 - Completer le premier lot `fra-kon`

**Objectif**

Ajouter un premier lot coherent de donnees texte et audio pour la paire `fra-kon`.

**Fichiers autorises**

- `data/raw/translation-pairs/fra-kon/text/contributions.csv`
- `data/raw/translation-pairs/fra-kon/audio/speakers.csv`
- `data/raw/translation-pairs/fra-kon/audio/manifests/contributions.tsv`
- fichiers audio sous `data/raw/translation-pairs/fra-kon/audio/clips/`

**Travail attendu**

- ajouter au moins 25 nouvelles paires de phrases
- ajouter les metadonnees des locuteurs utilises
- ajouter au moins 10 lignes de manifest audio valides
- documenter les variantes utiles dans `notes`

**Criteres d'acceptation**

- format CSV et TSV conforme au schema du projet
- correspondance exacte entre `transcript_text` et texte prononce
- aucune modification hors du dossier `fra-kon`

**Ne pas toucher**

- tout autre dossier que `fra-kon`

## Issue 3 - Completer le premier lot `fra-swa`

**Objectif**

Ajouter un premier lot coherent de donnees texte et audio pour la paire `fra-swa`.

**Fichiers autorises**

- `data/raw/translation-pairs/fra-swa/text/contributions.csv`
- `data/raw/translation-pairs/fra-swa/audio/speakers.csv`
- `data/raw/translation-pairs/fra-swa/audio/manifests/contributions.tsv`
- fichiers audio sous `data/raw/translation-pairs/fra-swa/audio/clips/`

**Travail attendu**

- ajouter au moins 25 nouvelles paires de phrases
- couvrir au moins 3 domaines parmi `daily_life`, `health`, `transport`, `education`, `commerce`
- ajouter au moins 10 enregistrements audio relies aux phrases ajoutees

**Criteres d'acceptation**

- metadonnees source et licence renseignees
- `source_lang` et `target_lang` corrects dans les deux sens si necessaire
- aucune modification hors du dossier `fra-swa`

**Ne pas toucher**

- tout autre dossier que `fra-swa`

## Issue 4 - Completer le premier lot `fra-lua`

**Objectif**

Ajouter un premier lot coherent de donnees texte et audio pour la paire `fra-lua`.

**Fichiers autorises**

- `data/raw/translation-pairs/fra-lua/text/contributions.csv`
- `data/raw/translation-pairs/fra-lua/audio/speakers.csv`
- `data/raw/translation-pairs/fra-lua/audio/manifests/contributions.tsv`
- fichiers audio sous `data/raw/translation-pairs/fra-lua/audio/clips/`

**Travail attendu**

- ajouter au moins 25 nouvelles paires de phrases
- ajouter les locuteurs relies aux clips ajoutes
- ajouter au moins 10 lignes audio valides dans le manifest
- utiliser des phrases naturelles, courtes et reutilisables

**Criteres d'acceptation**

- unicite des IDs texte et locuteur
- coherence entre `example_id`, `speaker_id` et `audio_path`
- aucune modification hors du dossier `fra-lua`

**Ne pas toucher**

- tout autre dossier que `fra-lua`

## Issue 5 - Documenter les langues et variantes de base

**Objectif**

Completer la documentation minimale de chaque langue suivie par le projet.

**Fichiers autorises**

- `data/raw/languages/fra/README.md`
- `data/raw/languages/lin/README.md`
- `data/raw/languages/kon/README.md`
- `data/raw/languages/swa/README.md`
- `data/raw/languages/lua/README.md`

**Travail attendu**

- documenter pour chaque langue :
  - nom de la langue
  - variantes ou dialectes suivis
  - systeme d'ecriture
  - remarques de normalisation
- garder un format simple et uniforme entre les 5 fichiers

**Criteres d'acceptation**

- chaque README contient les 4 rubriques minimales
- pas de changement dans `docs/`, `templates/` ou `data/raw/translation-pairs/`
- contenu coherent avec la politique de pivot actuelle

**Ne pas toucher**

- tout fichier hors de `data/raw/languages/`

## Notes de pilotage

- ouvrir ces 5 issues en meme temps est raisonnable car les zones d'ecriture ne se chevauchent pas
- eviter pour l'instant les issues transverses sur `README.md`, `CONTRIBUTING.md`, `templates/` ou sur le nettoyage global des datasets
- une fois ces 5 tickets lances, le lot suivant pourra porter sur la relecture, la validation et les checks de coherence
