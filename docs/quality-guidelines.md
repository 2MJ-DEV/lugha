# Directives qualite

## Objectif

Assurer que les donnees soient utiles pour l'entrainement et l'evaluation de systemes de traduction texte et voix.

## Texte

- la traduction doit transmettre le sens avant de coller mot a mot
- les fautes volontaires doivent etre signalees dans `notes`
- eviter les phrases trop longues au debut
- ajouter de la diversite grammaticale progressivement
- conserver les noms propres seulement s'ils sont utiles

## Audio

- voix intelligible
- debit naturel
- volume stable
- peu ou pas de bruit de fond
- une seule personne par fichier

## Relecture

Une entree devrait idealement passer par trois etats :

1. `draft`
2. `reviewed`
3. `validated`

## Cas difficiles

- si plusieurs traductions sont valides, garder la plus naturelle et expliquer les alternatives dans `notes`
- si une langue a plusieurs variantes importantes, le mentionner explicitement
- si une phrase depend fortement du contexte, ajouter une note courte
