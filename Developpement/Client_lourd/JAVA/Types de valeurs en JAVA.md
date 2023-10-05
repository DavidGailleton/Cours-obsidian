Il existe plusieurs type de valeurs dans le language [[JAVA]].
## Les types entiers

Il existe 4 types entiers signés en JAVA :

- `byte` **8 bits** la valeur minimale est de -128 et la valeur maximale est de 127
- `short` 16 bits
- `int` 32 bits
- `long` 64bits

Quand vous choisissez un type d'entier prenez en compte la valeur minimale et maximale que vous pouvez stocker dans la variable.

Vous pouvez aussi travailler avec des entiers non signées en utilisant des classes telles que **Integer** ou **Long**. Valeur max pour Long : 18 446 744 073 709 551 616

## Les types décimaux

Il existe 2 types décimaux en Java :

- `float` 32 bits
- `double` 64 bits

## Les types caracteres

Le type char est utilisé pour stocker un caractère unique. Une variable de type char utilise deux octets pour stocker le code [[Unicode]] du caractère. Dans le jeu de caractères Unicode, les 128 premiers caractères sont identiques au jeu de caractères ASCII, les caractères suivants, jusqu’à 255, correspondent aux caractères spéciaux de l’alphabet latin (par exemple les caractères accentués), le reste est utilisé pour les symboles ou les caractères d’autres alphabets.

Les caractères spécifiques ou ceux ayant une signification particulière pour le langage Java sont représentés par une séquence d’échappement. Elle est constituée du caractère \ suivi d’un autre caractère indiquant la signification de la séquence d’échappement. Le tableau suivant présente la liste des séquences d’échappement et leurs significations.

Sequence d'echappement

```java
    \b  Retour arrière
    \t  Tabulation horizontale
    \n  Saut de ligne
    \f  Saut de page
    \r  Retour chariot
    \"  Guillemet
    \'  Apostrophe
    \\  Antislash

    String s = "Ceci est une chai \" ne de caracteres";
```

Les caractères Unicode non accessibles au clavier sont eux aussi représentés par une séquence d’échappement constituée des caractères \u suivis de la valeur hexadécimale du code Unicode du caractère. Le symbole euro est par exemple représenté par la séquence \u20AC.

```java
char euro = '\u20AC';
```

Lien wiki : [https://fr.wikipedia.org/wiki/Table_des_caract%C3%A8res_Unicode](https://fr.wikipedia.org/wiki/Table_des_caract%C3%A8res_Unicode)