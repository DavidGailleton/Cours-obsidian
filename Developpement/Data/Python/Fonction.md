Une **fonction** est un bloc de code avec un but spécifique, auquel vous pouvez donner un nom. Quand vous **appelez** cette fonction, vous exécutez le code qu’elle contient. Les fonctions vous laissent saisir des **paramètres** pour exécuter le même code sur différentes valeurs.  

Il y a différents types de fonctions dans Python :

1. Les fonctions intégrées fournies avec Python.
    
2. Les fonctions définies par l’utilisateur que les développeurs (vous !) créent.

Il y a 3 types de fonction :
1. Les [[#Fonction sans paramètres]]
    
2. Les [[#fonction avec paramètres]].
    
3. Les [[#fonction avec une valeur de retour]].

## Definition d'un fonction
Les fonctions sont des blocs de code réutilisables qui permettent d'organiser et de structurer le code, ainsi que de faciliter sa maintenance. En Python, la création d'une fonction se fait à l'aide du mot-clé  `def`  , suivi du nom de la fonction et des éventuels paramètres entre parenthèses.

## Fonction sans paramètres

Une fonction **sans** paramètres et sans valeur de retour est la fonction la plus basique que l'on puisse créer en programmation. Elle est assimilable à un **bloc de code** à lancer quand cela est nécessaire. Elle est utile pour **encapsuler** un bloc de code répétitif, et faciliter sa réutilisation dans différents endroits du programme.

```python
def afficher_message():
    print("Bonjour, comment ça va ?")
```

Cette fonction s'appelle  `afficher_message`  et ne prend aucun paramètre en entrée, car elle est définie avec des parenthèses vides. Elle n'a pas de valeur de retour car elle se contente d'afficher un message à l'écran en utilisant la fonction  `print()`  .

Pour appeler cette fonction, il suffit d'utiliser **son nom** et les **parenthèses** vides, car il n’y a pas de paramètres :

```python
afficher_message()
```

En utilisant cette fonction dans votre code, vous pouvez facilement afficher un message de salutation, comme `"Bonjour, comment ça va ?"`, autant de fois que nécessaire, simplement en l'appelant dans le code.

## fonction avec paramètres
On peut également créer une fonction avec des **paramètres**, qui permettent de transmettre des valeurs à la fonction. Les paramètres sont simplement listés entre parenthèses, séparés par des virgules. Voici un exemple d'une fonction qui prend deux paramètres, un nom et un prénom, et qui les affiche ensuite.

```python
def afficher_nom_prenom(nom, prenom):
    print("Nom :", nom)
    print("Prénom :", prenom)
```

Pour appeler cette fonction, il faut préciser les valeurs à transmettre aux paramètres, soit deux chaînes de caractères.

```python
afficher_nom_prenom("Dupont", "Jean")
```

La fonction affichera :

> Nom : Dupont
> Prénom : Jean

## fonction avec une valeur de retour
Une fonction avec une valeur de **retour** est une fonction qui peut prendre des **paramètres** et effectuer des opérations, mais qui renvoie également une valeur à la fin. Cette valeur peut être utilisée à d'autres endroits du programme. Par exemple, si nous avons une fonction qui calcule la somme de deux nombres, nous pouvons stocker le résultat dans une variable pour l'utiliser plus tard dans notre programme.
![[16827900709796_image4.png]]
```python
def calculer_somme(a, b):
  resultat = a + b
  return resultat
```

Dans cet exemple, la fonction prend deux nombres en paramètres, les additionne, puis **renvoie** le résultat de l'addition. Le résultat est stocké dans la variable  `resultat`  et est renvoyé à l'aide du mot-clé  `return`  .

Pour utiliser la valeur de retour de la fonction, nous pouvons stocker le résultat dans une variable, comme ceci :

```python
somme = calculer_somme(2, 3)
print(somme) #Ce print affichera 5
```

> Est-ce qu’une fonction peut renvoyer plusieurs valeurs simultanément ?

Il est possible de retourner **plusieurs** valeurs en les **séparant** par des **virgules** dans l'instruction de retour de la fonction. Les valeurs retournées seront automatiquement regroupées dans un [[Tulpes]].

## Quand utiliser les fonctions

Quand on écrit beaucoup de code, on s’y perd et on fait des erreurs facilement entre les différentes fonctionnalités en cours. Les fonctions vous aident à séparer le code en sections plus petites. Comme ça, vous gardez le fil sur ce que chaque partie est censée faire.

Vous en sortirez avec un code mieux écrit, mieux structuré et plus lisible