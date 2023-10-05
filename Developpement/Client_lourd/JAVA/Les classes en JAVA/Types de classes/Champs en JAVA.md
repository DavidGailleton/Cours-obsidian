La création de champs fait une syntaxe particulière : 

``` java
[private | protected | public] typeDeVariable nomDeLaVariable;
```

Il est possible de créer des variables de la classe avec le mot `static` et des constantes avec `final`.

``` java
public class Personne {
	private String nom;
	private String prenom;
	private int age;
}
```

Les portées :
- private : la variable est visible uniquement dans la classe
- protected : la variable est visible dans la classe et dans les classes filles, ainsi que dans le package
- public : la variable est visible partout

Si vous oubliez de preciser une portée, la portée par defaut est package.

