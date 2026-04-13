# Schema du dataset

## 1. Organisation generale

Le projet distingue deux niveaux :

- `data/raw/` : donnees brutes collectees
- `data/processed/` : donnees nettoyees, normalisees et prêtes pour usages modeles

Les contributeurs humains travaillent d'abord dans `data/raw/`.

## Politique de pivot

Dans la phase actuelle :

- `fra` est le pivot principal
- les paires actives sont `fra-lin`, `fra-kon`, `fra-swa`, `fra-lua`
- les paires avec `eng` ne sont pas prioritaires pour la collecte principale

Des jeux avec l'anglais peuvent etre ajoutes ensuite, mais seulement apres validation suffisante des paires avec pivot francais.

## 2. Dataset texte brut

Dans `data/raw/translation-pairs/<pair>/text/`, le fichier principal est :

```text
contributions.csv
```

Chaque ligne represente une contribution brute. Elle peut etre relue, corrigee, dedoublonnee ou reclassifiee plus tard.

Chaque fichier CSV de `text/` doit utiliser les colonnes suivantes :

```text
example_id,source_lang,target_lang,source_text,target_text,domain,register,source_type,source_name,source_url,license,translator,review_status,notes
```

### Description des colonnes

- `example_id` : identifiant unique de l'exemple
- `source_lang` : code langue source, par exemple `fra`
- `target_lang` : code langue cible, par exemple `lin`
- `source_text` : phrase d'origine
- `target_text` : traduction
- `domain` : domaine, par exemple `health`, `transport`, `daily_life`
- `register` : `formal`, `neutral`, `informal`
- `source_type` : `original`, `public_domain`, `licensed`, `community`
- `source_name` : nom de la source
- `source_url` : lien vers la source si applicable
- `license` : licence ou statut d'usage
- `translator` : nom ou pseudo du contributeur
- `review_status` : `draft`, `reviewed`, `validated`
- `notes` : remarques sur variante, ambiguite ou contexte

## 3. Metadonnees par langue

Chaque dossier `data/raw/languages/<code>/README.md` documente :

- nom de la langue
- variantes ou dialectes suivis
- systeme d'ecriture
- remarques de normalisation

## 4. Dataset audio brut

### Fichier `audio/speakers.csv`

Colonnes :

```text
speaker_id,language_code,display_name,gender,age_range,country,region,accent_or_variant,consent_status,license,contact_public,notes
```

### Fichier manifest `.tsv`

Colonnes :

```text
audio_path	example_id	speaker_id	transcript_lang	transcript_text	duration_seconds	sample_rate	horizontal_review	status	notes
```

### Description

- `audio_path` : chemin relatif vers le fichier audio
- `example_id` : identifiant de la phrase lue
- `speaker_id` : identifiant du locuteur
- `transcript_lang` : langue du transcript
- `transcript_text` : texte prononce
- `duration_seconds` : duree
- `sample_rate` : frequence d'echantillonnage
- `horizontal_review` : verification croisee par un autre collaborateur
- `status` : `draft`, `reviewed`, `validated`
- `notes` : bruit, hesitations, variante, reprise

Dans `data/raw/translation-pairs/<pair>/audio/manifests/`, le fichier principal est :

```text
contributions.tsv
```

## 5. Dataset traite pour modeles

Une fois les donnees nettoyees, les exports destines aux modeles pourront etre places dans :

```text
data/processed/training-ready/text/
data/processed/training-ready/audio/
```

Exemples de sorties attendues plus tard :

- `train.csv`
- `validation.csv`
- `test.csv`
- manifests audio alignes et verifies

Regles :

- ne pas dupliquer une meme phrase dans plusieurs jeux
- ne pas melanger donnees brutes et donnees preparees
- garder une trace de l'origine des donnees nettoyees a partir des IDs bruts
