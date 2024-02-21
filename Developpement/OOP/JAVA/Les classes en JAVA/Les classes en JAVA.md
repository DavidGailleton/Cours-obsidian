Les classes en [[JAVA]] sont representées sous forme de diagramme UML (Unified Modeling Language).

https://www.uml.org/

[[UML]] est un language graphique qui permet de representer les concepts de la programmation Objet

Les classes peuvent être des :
- [[Champs en JAVA|Champs]]
- [[Methodes (Programmation orienté objet)|Methodes]]
- [[Les packages en JAVA|Packages]]
- [[Les collections en JAVA|Collections]]
	- [[Listes (list)|Listes]]
## La création d'une classe

Le création d'une classe passe par la déclaration de la classe elle-même et de tous les éléments la constituant

Une classes est constitué de :
- [[Modificateurs]]

### Déclaration d'une classe

```java
[modificateurs] class NomDeLaClasse [extends NomDeLAClasseDeBase] [implements NomDinterface1, NomDinterface2] {
	Code de la classe
}
```

### Appel d'un classe
Pour appeler un classe on utilise un [[Constructeurs en JAVA|Constructeurs]]
```java
class Personne {
    //...
    public Personne() {
        //...
    }
}

Personne ayoub = new Personne();
```
## Création d'accesseur (getter et setter)

La déclaration des attributs avec une visibilité privée est une bonne pratique pour respecter le principe d’encapsulation. Toutefois, cette solution est limitative puisque seul le code de la classe où ils sont déclarés peut y accéder. Pour pallier ce problème, vous devez mettre en place des accesseurs. Ce sont des fonctions ordinaires qui ont simplement pour but de rendre visibles les champs à partir de l’extérieur de la classe.
Par convention, les fonctions chargées d’affecter une valeur à un champ sont nommées set suivi du nom du champ, les fonctions chargées de fournir la valeur d’un champ sont nommées get suivi du nom du champ. Si le champ est de type boolean, le préfixe get est remplacé par le préfixe is. 
Si un champ doit être en lecture seule, l’accesseur set ne doit pas être disponible, si un champ doit être en écriture seule alors c’est la fonction get qui doit être omise. Les accesseurs sont communément appelés getters et setters. Avec cette technique, vous pouvez contrôler l’utilisation qui sera faite des champs d’une classe. 

Nous pouvons donc modifier la classe Personne en y ajoutant quelques règles de gestion :
Le nom doit être en majuscules.
Le prénom doit être en minuscules.

```java
class Personne
{
    private String nom;
    private String prenom;

    public String getNom() {
        return nom;
    }

    public void setNom(String nom) {
        this.nom = nom.toUpperCase();
    }
}
```



## Les génériques

Il est possible de créer des [[Les génériques en JAVA|génériques]]
## Les collections

Les collections sont des classes qui permettent de stocker des objets.