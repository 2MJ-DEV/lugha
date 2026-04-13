# Exemples de contribution

## Objectif

Ce document montre a quoi ressemble une contribution minimale correcte pour :

- le texte
- les metadonnees locuteur
- le manifest audio

## Exemple 1 : contribution texte

Fichier :

`data/raw/translation-pairs/fra-lin/text/contributions.csv`

Exemple :

```csv
example_id,source_lang,target_lang,source_text,target_text,domain,register,source_type,source_name,source_url,license,translator,review_status,notes
fra-lin-000001,fra,lin,Bonjour.,Mbote.,daily_life,neutral,original,,,CC-BY-4.0,alice,draft,
fra-lin-000002,lin,fra,Nzala ezali koboma ngai.,J'ai tres faim.,daily_life,neutral,community,,,CC-BY-4.0,bob,reviewed,Expression naturelle en lingala courant
```

Explication :

- `example_id` doit etre unique
- `source_lang` et `target_lang` doivent correspondre au sens reel de la traduction
- `review_status` peut commencer par `draft`

## Exemple 2 : contribution locuteur audio

Fichier :

`data/raw/translation-pairs/fra-lin/audio/speakers.csv`

Exemple :

```csv
speaker_id,language_code,display_name,gender,age_range,country,region,accent_or_variant,consent_status,license,contact_public,notes
speaker-lin-001,lin,alice_voice,female,adult,CD,Kinshasa,Kinshasa,granted,CC-BY-4.0,,Voix claire
speaker-fra-001,fra,bob_voice,male,adult,CD,Goma,standard,granted,CC-BY-4.0,,Lecture lente et nette
```

Explication :

- un locuteur = une ligne
- `speaker_id` doit rester stable dans le temps
- `consent_status` doit indiquer que la personne a accepte

## Exemple 3 : contribution audio

Fichiers :

- clip audio dans `data/raw/translation-pairs/fra-lin/audio/clips/`
- manifest dans `data/raw/translation-pairs/fra-lin/audio/manifests/contributions.tsv`

Exemple de nom de fichier audio :

```text
speaker-lin-001_fra-lin-000001.wav
```

Exemple de ligne manifest :

```tsv
audio_path	example_id	speaker_id	transcript_lang	transcript_text	duration_seconds	sample_rate	horizontal_review	status	notes
audio/clips/speaker-lin-001_fra-lin-000001.wav	fra-lin-000001	speaker-lin-001	lin	Mbote.	1.20	16000		draft	Voix propre
```

Explication :

- `audio_path` est relatif au dossier de la paire
- `example_id` doit pointer vers une phrase existante dans `text/contributions.csv`
- `transcript_text` doit correspondre exactement a ce qui est prononce

## Exemple 4 : mini flux complet

1. Ajouter une phrase dans `text/contributions.csv`
2. Ajouter le locuteur dans `audio/speakers.csv`
3. Enregistrer le clip dans `audio/clips/`
4. Declarer le clip dans `audio/manifests/contributions.tsv`

## Exemple deja present dans le depot

Le depot contient maintenant un exemple minimal dans :

- [data/raw/translation-pairs/fra-lin/text/contributions.csv](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/data/raw/translation-pairs/fra-lin/text/contributions.csv:1)
- [data/raw/translation-pairs/fra-lin/audio/speakers.csv](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/data/raw/translation-pairs/fra-lin/audio/speakers.csv:1)
- [data/raw/translation-pairs/fra-lin/audio/manifests/contributions.tsv](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/data/raw/translation-pairs/fra-lin/audio/manifests/contributions.tsv:1)
