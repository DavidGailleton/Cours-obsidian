Les constructeurs sont utilisés pour initialiser l’état de l’objet. Comme les méthodes, un constructeur contient également une collection d'instructions qui sont exécutées au moment de la création de l'objet.

Chaque fois qu'un objet est créé à l'aide du mot-clé **new**, au moins un constructeur (il peut s'agir d'un constructeur par défaut) est appelé pour affecter des valeurs initiales aux données membres de la même classe.  
Un constructeur est appelé lors de la création d'un objet ou d'une instance.

#### Exemple 1 :
```java
class Personne {
    //...
    public Personne() {
        //...
    }
}

Personne ayoub = new Personne();
```
### Règles pour définir un Constructeur

- Les constructeurs d'une classe doivent avoir le même nom que le nom de la [[Les classes en JAVA|classe]] dans laquelle elle réside.
- Un constructeur en Java ne peut pas être abstrait, final, statique et synchronisé.
- Les modificateurs d’accès peuvent être utilisés dans la déclaration du constructeur pour contrôler son accès, c’est-à-dire quelle classe peut appeler le constructeur.