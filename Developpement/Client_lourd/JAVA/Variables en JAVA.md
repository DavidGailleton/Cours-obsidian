En [[JAVA]] on peut déclarer une [[Developpement/Commun/Variables|variable]] a peu près n'importe ou dans notre programme. Par contre elle doivent être declarer obligatoirement entre les accolades d'une classe, interface ou enum.

```java
public class MaClasse {

	// variable d'instance
	//Pour declarer une variable il faut une portee
	//un type et un nom
	private int variableInstance;

	//variable de classe
	private static int variableClasse;

	//methode pour declarer une methode il faut une portee, un type de retour, un nom, des parametres (optionnel)
	public void maMethode(int parametre) {
		int variableLocale = 0;
	}
}
```

## Le nom des variable :

- doit commencer par une lettre ou un underscore
- ne doit pas contenir d'espace
- ne doit pas contenir de caractere speciaux
- ne doit pas etre un mot cle du language
- [[camelCase]] ou [[PascalCase]]

## le type de variable :

Il existe deux categories de types de variable :
- les types valeurs
- les types references

Les types valeurs, ils sont au nombre de sept et on les organise en 4 catégories:
les num entiers, les decimaux, les caracteres et les booleens.

## La declaration des variables :

```java
[modificateur] type nomVariable;

```
Il est possible de déclarer plusieur variable en meme temp
```java
type variable, variable2, variable3;
```

Exemples de déclaration de variable :
```java
int i;
Date today;
String name, firstname;
```
## Initialisation des variables

```java
int i = 0; //declaration + initialisation

or

int i; // declaration
i = 0; // initialisation
```

## L'affectation

```java
nomVariable = nouvelleValeur;


int i; // declaration
i = 0; // initialisation
i = 2: // affectation
```

