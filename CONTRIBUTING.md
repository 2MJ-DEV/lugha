# Contribuer a Lugha

Ce projet accepte des contributions texte, audio et documentation.

## Principe important

Le depot collecte d'abord des donnees brutes. Les contributions vont en premier lieu dans `data/raw/`.

Le nettoyage, la normalisation et la preparation des jeux pour l'entrainement se feront ensuite dans `data/processed/`.

## Regle de pivot

Pour l'etape actuelle du projet :

- le pivot actif est le francais (`fra`)
- les contributions prioritaires sont `fra` <-> `lin`, `kon`, `swa`, `lua`
- l'anglais (`eng`) n'est pas encore un pivot de collecte principal

Des contributions impliquant l'anglais peuvent etre envisagees plus tard, mais seulement lorsque les jeux bases sur le francais seront suffisamment valides et corrects.

## Types de contribution

- ajout de phrases sources
- traduction vers une ou plusieurs langues
- relecture et correction
- alignement texte/audio
- enregistrement vocal
- verification de qualite
- documentation et normalisation

## Processus recommande

1. Choisir une langue ou une paire de langues.
2. Verifier le dossier correspondant dans `data/raw/translation-pairs/`.
3. Ajouter ou corriger les donnees sans changer les colonnes existantes.
4. Documenter la source, le domaine et les remarques utiles.
5. Relire avant de proposer la contribution.

Des exemples concrets sont disponibles dans [docs/contributor-examples.md](/c:/Users/HP/Dev/05_OPEN_SOURCE/contributions/lugha/docs/contributor-examples.md).

## Conventions generales

- Encodage : `UTF-8`
- Separateur CSV : virgule
- Une ligne = un seul exemple
- Une phrase doit rester naturelle et grammaticalement correcte
- Eviter les doublons exacts
- Conserver la ponctuation utile
- Utiliser des identifiants stables et uniques
- Ne jamais melanger plusieurs phrases dans une meme cellule si cela peut etre evite

## Organisation des dossiers

- `data/raw/` : depot principal des contributions communautaires
- `data/processed/` : donnees derivees, nettoyees et pretes pour les modeles
- ne pas melanger les fichiers bruts et les fichiers nettoyes
- ne pas traiter `eng` comme pivot principal a ce stade

## Regles pour les textes

- privilegier des phrases utiles dans la vie reelle
- couvrir plusieurs domaines : salutation, sante, commerce, transport, education, administration, technologie
- indiquer le registre si necessaire : `formal`, `neutral`, `informal`
- signaler les variantes regionales dans la colonne `notes`
- si une traduction n'est pas litterale mais plus naturelle, la garder et l'expliquer si besoin

## Regles pour l'audio

- demander le consentement explicite du locuteur
- ne pas publier d'audio de tiers sans autorisation
- preferer des enregistrements clairs, sans musique ni bruit fort
- un fichier audio doit correspondre a une seule phrase
- garder le nom de fichier declare dans le manifest
- si possible, utiliser `wav` 16 kHz mono ou un format documente de facon coherente

## Nommage

### IDs de phrases

Format recommande :

```text
fra-lin-000001
fra-lin-000002
```

### IDs de locuteurs

Format recommande :

```text
speaker-lin-001
speaker-fra-001
```

### Fichiers audio

Format recommande :

```text
speaker-lin-001_fra-lin-000001.wav
```

## Sources et licence

- si vous avez ecrit la phrase vous-meme, indiquer `source_type=original`
- si vous utilisez une source externe, verifier que la licence autorise la reutilisation
- noter clairement `source_name`, `source_url` et `license`

## Ce qu'il faut eviter

- contenus proteges sans autorisation
- donnees medicales ou personnelles identifiables
- insultes gratuites, contenu haineux ou violent non justifie
- phrases artificielles incomprehensibles
- traductions mot-a-mot non naturelles sans justification

## Avant soumission

- verifier les colonnes
- verifier l'orthographe
- verifier l'alignement entre texte et audio
- verifier l'unicite des identifiants
- verifier que les chemins audio declares existent bien
- verifier que les nouvelles donnees sont ajoutees dans `data/raw/`
- verifier que la contribution respecte la politique de pivot du projet
