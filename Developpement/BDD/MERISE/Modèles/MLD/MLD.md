Le modèle logique de données MLD possède 4 regles

## Regle 1: entité
En règle générale, toute entité du MCD devient une relation dont la clef est l'identifiant de cette entité.
Chaque propriété de l'entité devient un attribut de la relation correspondante.

Pays (**id_P**, nom_p)

## Règle 2: conversion d'associations n'ayant que des cardinalités de type 0/1,N

Une association ayant des cardinalités O,N ou 1 de part et d'autre devient une relation dont
la clef est constituée des identifiants des entités reliées par cette association.

Ces identifiants seront donc également des clefs étrangères respectives.

On parle de relations associatives.
![[Pasted image 20231207093048.png]]
Rédiger (**#id_a**, **#id_i**, nb_chapitre)

## Règle 3: conversion des associations ayant au moins une cardinalité de type 1,1

Plusieurs possibilités s'offrent à nous pour ce cas de figure.

La règle de conversion la plus répandue aujourd'hui est d'ajouter une clef étrangère dans
la relation qui correspond à l'entité se situant du côté de cette cardinalité 1,1.
![[Pasted image 20231207093243.png]]
Pays (**id_p**)
Auteur (**id_a**, nom_a, prenom_a, data_naissance_a, `#id_p`)

## Règle 4: conversion des associations ayant au moins une cardinalité de type 0,1

Créer une relation associative qui serait identifié de la même façon que pour une cardinalité 1,1.
La pertinence de l'une ou l'autre méthode varie en fonction du nombre d'occurrences caractérisées par la cardinalité 0 ou la cardinalité 1.

En effet, lorsque les occurrences avec la cardinalité 1 sont plus nombreuses que les occurrences avec la cardinalité 0, la première méthode est préférable.
![[Pasted image 20231207093507.png]]
Categorie (**id_cat**, libelle_cat)
Livre (**id_l**, titre_l, annee_l, resume_l)
appartenir (**#id_cat**, **#id_l**)

De même que pour les cardinalités 1,1, une association ayant une cardinalité 0,1 doit être binaire, et les deux mêmes possibilités s'offrent à nous .

Créer la clef étrangère dans la relation correspondant à l'entité du côté de la cardinalité 0,1. 

Rappelons que dans ce cas, l'association ne peut pas être porteuse de données.
![[Pasted image 20231207093737.png]]
Categorie (**id_cat**, libelle_cat)
Livre (**id_l**, titre_l, annee_l, resume_l, `#id_cat`)
