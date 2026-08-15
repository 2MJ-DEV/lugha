# Audio $pairName

Ce dossier est reserve aux contributions audio brutes pour la paire $pairName.

## Organisation

- clips/ : fichiers audio bruts fournis par les contributeurs
- speakers.csv : metadonnees des locuteurs
- manifests/contributions.tsv : manifest brut des clips audio

Les manifests 	rain.tsv, alidation.tsv et 	est.tsv ne sont pas maintenus dans data/raw/.
Ils seront generes plus tard dans data/processed/training-ready/audio/ apres verification et nettoyage.

## Regles

- un clip audio doit correspondre a une seule phrase
- example_id doit pointer vers une ligne existante dans 	ext/contributions.csv
- udio_path doit etre relatif au dossier de la paire
- declarer le locuteur dans speakers.csv avant d'ajouter ses clips au manifest
- laisser les champs de revue vides tant que le clip n'a pas ete verifie