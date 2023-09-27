Exercice 1

Créer un tableau de dix chaînes de caractères puis remplir ce tableau avec des adresses e-mail. Calculer ensuite, à partir des informations présentes dans le tableau, la part de marché de chacun des fournisseurs.

Indice : dans une adresse e-mail, le nom du fournisseur est la partie située après le caractère @.

Exercice 2

Générer trois nombres aléatoires compris entre 0 et 1000, puis vérifier si vous avez deux nombres pairs suivis par un nombre impair. Si ce n’est pas le cas, recommencer jusqu’à ce que vous ayez la combinaison pair, pair, impair. Afficher ensuite le nombre d’essais nécessaires pour obtenir cette combinaison.

Indice : la classe Random propose un ensemble de méthodes permettant d’obtenir un nombre aléatoire. Concentrez-vous sur la méthode suivante en lisant la javadoc :

```java
public int nextInt(int bound)
```

Pour utiliser cette méthode, il est nécessaire d’avoir un objet de type Random :

```java
Random rd = new Random();
rd.nextInt(...);
```

```

```
