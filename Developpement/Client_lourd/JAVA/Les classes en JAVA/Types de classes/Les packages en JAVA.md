Le but principal des packages est l’organisation et le rangement des classes et interfaces d’une application. Le principe est le même que dans la vie courante. Si vous avez un grand placard dans votre maison, il est évident que l’installation d’étagères dans ce placard va faciliter l’organisation et la recherche des objets qui y sont rangés par rapport à un stockage en "vrac". 

L’organisation des classes en packages apporte les avantages suivants :
- Facilité pour retrouver et réutiliser un élément
- Limitation des risques de conflits de noms

Création d’une nouvelle visibilité (la visibilité package) en plus des visibilités standards (private, protected, public). Lorsqu’un élément (une classe, un champ, une méthode) ne présente pas de modificateurs de visibilité, alors cet élément n’est visible que par les éléments présents dans le même package. Il existe une subtilité pour les éléments protégés (champs, méthodes). Ils sont bien sûr accessibles dans les classes dérivées, mais aussi dans les classes du même package.

## Comment créer un package ?

La première chose à faire lorsque l’on souhaite créer un package est de lui trouver un nom. Ce nom doit être choisi avec précaution pour permettre au package de remplir pleinement son rôle. Il doit être unique et représentatif des éléments stockés à l’intérieur.

Pour assurer l’unicité du nom d’un package, on utilise par convention le nom de domaine de l’entreprise en inversant l’ordre des éléments comme première partie pour le nom du package.

```java
    isitech.fr
    fr.isitech

    ecole-isitech.fr

    fr.ecole_isitech.compta.Client

    fr.ecole_isitech.reseau.Client
```

Pour importer la classe Client dans une autre classe, il faut utiliser l’instruction import.

```java
    import fr.ecole_isitech.compta.Client;

    import fr.ecole_isitech.compta.*;

    import fr.*;
```