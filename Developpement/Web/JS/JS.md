
# Les bases du JavaScript:
JavaScript est un langage de programmation populaire utilisé pour créer des pages web interactives. Comprendre les variables, les types de données et les opérateurs est essentiel pour écrire du code JavaScript efficace.

## Les variables en JavaScript

Les variables sont des éléments fondamentaux de la programmation. En JavaScript, les variables sont utilisées pour stocker des valeurs qui peuvent être utilisées dans le code. Les variables en JavaScript peuvent contenir n'importe quel type de données, y compris des nombres, des chaînes de caractères et des booléens.

Pour déclarer une variable en JavaScript, utilisez le mot clé "var", suivi du nom de la variable et de la valeur à lui attribuer :

``` javascript
var maVariable = "Bonjour";
```
Dans l'exemple ci-dessus, nous avons créé une variable nommée "maVariable" et lui avons assigné la valeur "Bonjour". Cette variable peut maintenant être utilisée dans le reste du code.

Il est important de noter que les noms de variables en JavaScript sont sensibles à la casse. Par exemple, la variable "maVariable" est différente de la variable "MaVariable".

Les variables sont utilisées pour stocker des données dans les programmes JavaScript. Lors de la déclaration d'une variable, il est important de comprendre la différence entre les déclarations "let", "const" et "var".

## La déclaration "var"

La déclaration "var" a été la première façon de déclarer des variables en JavaScript. Elle a été utilisée depuis les premières versions du langage. Elle permet de déclarer une variable qui peut être modifiée et réaffectée à tout moment.

Par exemple, nous pouvons déclarer une variable "age" de la manière suivante :

``` javascript
var age = 30;
```
Nous pouvons ensuite modifier la valeur de cette variable :
``` javascript
age = 31;
```
Cependant, il est important de noter que la portée d'une variable déclarée avec "var" est celle de la fonction courante ou la portée globale si elle est déclarée à l'extérieur d'une fonction. Cela peut entraîner des erreurs si plusieurs variables portent le même nom.

## Les déclarations "let" et "const"

Les déclarations "let" et "const" ont été introduites dans les versions plus récentes de JavaScript (à partir de ECMAScript 6). Elles sont utilisées pour déclarer des variables qui sont strictement limitées à la portée de leur bloc de code.

La déclaration "let" permet de déclarer une variable qui peut être réaffectée à tout moment, mais qui est limitée à la portée de son bloc de code :


``` javascript
let age = 30;
age = 31; // ceci est autorisé car la variable a été déclarée avec "let"
```

La déclaration "const", quant à elle, permet de déclarer une variable qui ne peut pas être réaffectée à une nouvelle valeur une fois qu'elle a été définie. Cette variable est également limitée à la portée de son bloc de code :

``` javascript
const age = 30;
age = 31; // ceci générera une erreur car la variable a été déclarée avec "const"

```

Il est important de noter que lors de l'utilisation de "const", la variable ne peut pas être réaffectée à une nouvelle valeur, mais cela ne signifie pas que la valeur elle-même ne peut pas être modifiée. Par exemple, si nous déclarons une constante tableau, nous pouvons toujours modifier les éléments individuels du tableau :
``` javascript
const tableau = [1, 2, 3];
tableau.push(4); // ceci est autorisé car nous ne réaffectons pas la variable elle-même
```

## Les avantages de "let" et "const"

Les déclarations "let" et "const" présentent plusieurs avantages par rapport à la déclaration "var" :

-   Elles permettent de mieux contrôler la portée des variables.
-   Elles réduisent les risques d'erreurs en cas de réutilisation de noms de variables.
-   Elles permettent de mieux gérer les valeurs immuables en utilisant "const".


En résumé, les déclarations "let" et "const" offrent des avantages importants par rapport à "var". Elles permettent de mieux contrôler la portée des variables, ce qui réduit les risques d'erreurs et facilite la maintenance du code. La déclaration "const" permet également de mieux gérer les valeurs immuables, ce qui peut être utile dans certains cas.

En conclusion, il est recommandé d'utiliser les déclarations "let" et "const" plutôt que "var" dans les nouveaux projets JavaScript. Cela permet de profiter des avantages de ces déclarations plus modernes et d'éviter les erreurs liées à la portée des variables et à la réutilisation des noms de variables.




## Les types de données en JavaScript

JavaScript prend en charge plusieurs types de données différents. Les types de données les plus courants sont :

-   Les chaînes de caractères (string) : utilisées pour stocker du texte.
-   Les nombres (number) : utilisés pour stocker des nombres.
-   Les booléens (boolean) : utilisés pour stocker des valeurs vraies ou fausses.
-   Les tableaux (array) : utilisés pour stocker plusieurs valeurs dans une seule variable.
-   Les objets (object) : utilisés pour stocker des données complexes.

Pour déterminer le type de données d'une variable en JavaScript, utilisez l'opérateur "typeof" :

``` javascript
var maVariable = "Bonjour";
console.log(typeof maVariable); // affichera "string" dans la console

```
Dans l'exemple ci-dessus, nous avons utilisé l'opérateur "typeof" pour déterminer le type de données de la variable "maVariable". Le résultat affiché dans la console est "string".








## Les opérateurs en JavaScript

Les opérateurs sont utilisés pour effectuer des calculs ou des opérations sur les valeurs stockées dans les variables. Les opérateurs les plus courants en JavaScript sont :

-   L'addition (+) : utilisée pour ajouter des nombres ou concaténer des chaînes de caractères.
-   La soustraction (-) : utilisée pour soustraire des nombres.
-   La multiplication (*) : utilisée pour multiplier des nombres.
-   La division (/) : utilisée pour diviser des nombres.
-   Le modulo (%) : utilisé pour obtenir le reste d'une division.

``` javascript
var nombre1 = 10;
var nombre2 = 5;

var somme = nombre1 + nombre2;
console.log(somme); // affichera 15 dans la console

var difference = nombre1 - nombre2;
console.log(difference); // affichera 5 dans la console

var produit = nombre1 * nombre2;
console.log(produit); // affichera 50 dans la console

var quotient = nombre1 / nombre2;
console.log(quotient); // affichera 2 dans la console

var reste = nombre1 % nombre2

```
## Les chaines de caracteres

Les chaînes de caractères sont utilisées pour représenter du texte dans les programmes JavaScript. Dans cette partie du cours, nous allons explorer les différentes opérations que vous pouvez effectuer sur les chaînes de caractères en JavaScript.


### Création d'une chaîne de caractères

En JavaScript, les chaînes de caractères (ou strings) sont utilisées pour stocker et manipuler du texte. Une chaîne de caractères est une séquence de caractères entre guillemets simples (' ') ou doubles (" ").
Les chaînes de caractères en JavaScript sont des objets, ce qui signifie qu'elles ont des propriétés et des méthodes qui peuvent être utilisées pour effectuer des opérations sur les chaînes.

En JavaScript, vous pouvez créer une chaîne de caractères en utilisant des guillemets simples ou doubles :
``` javascript
let texte1 = 'Ceci est une chaîne de caractères';
let texte2 = "Ceci est une autre chaîne de caractères";
```

Vous pouvez également créer une chaîne de caractères en utilisant la méthode "toString()" sur un objet :

``` javascript
let nombre = 123; let texte3 = nombre.toString();
```

### Concaténation de chaînes de caractères

La concaténation de chaînes de caractères est l'opération qui permet de combiner plusieurs chaînes de caractères en une seule. En JavaScript, vous pouvez concaténer des chaînes de caractères en utilisant l'opérateur "+" :

``` javascript
let nom = 'Jean'; let prenom = 'Dupont'; let nomComplet = nom + ' ' + prenom;
```
Il est également possible de concaténer des chaînes de caractères en utilisant la méthode "concat()" :

``` javascript
let nom = 'Jean';
let prenom = 'Dupont';
let nomComplet = nom.concat(' ', prenom);

```
### Longueur d'une chaîne de caractères

La longueur d'une chaîne de caractères est le nombre de caractères qu'elle contient. En JavaScript, vous pouvez obtenir la longueur d'une chaîne de caractères en utilisant la propriété "length" :

``` javascript
let texte = 'Ceci est une chaîne de caractères';
let longueur = texte.length;
```


### Accès aux caractères individuels d'une chaîne

En JavaScript, vous pouvez accéder aux caractères individuels d'une chaîne en utilisant la notation des crochets. Le premier caractère d'une chaîne a un index de 0, le deuxième caractère a un index de 1, et ainsi de suite :

``` javascript
let texte = 'Ceci est une chaîne de caractères';
let premierCaractere = texte[0];
let deuxiemeCaractere = texte[1];

```

Il est également possible d'accéder aux caractères individuels d'une chaîne en utilisant la méthode "charAt()" :


``` javascript
let texte = 'Ceci est une chaîne de caractères';
let premierCaractere = texte.charAt(0);
let deuxiemeCaractere = texte.charAt(1);

```

### Recherche dans une chaîne de caractères

En JavaScript, vous pouvez rechercher un texte spécifique dans une chaîne de caractères en utilisant la méthode "indexOf()". Cette méthode renvoie l'index de la première occurrence du texte spécifié, ou -1 si le texte n'est pas trouvé :


``` javascript
let texte = 'Ceci est une chaîne de caractères';
let position = texte.indexOf('chaîne');
```

Il est également possible de rechercher la dernière occurrence d'un texte spécifique en utilisant la méthode "lastIndexOf()".

Vous pouvez utiliser beaucoup d'autres methodes : 
``` javascript
let message = "Bonjour tout le monde !";
console.log(message.toLowerCase()); // affiche "bonjour tout le monde !"
console.log(message.toUpperCase()); // affiche "BONJOUR TOUT LE MONDE !"
console.log(message.slice(3, 9)); // affiche "jour t"

```

La méthode `toLowerCase()` convertit tous les caractères d'une chaîne en minuscules, tandis que `toUpperCase()` les convertit en majuscules.

La méthode `indexOf()` renvoie l'index (ou la position) de la première occurrence d'une sous-chaîne dans une chaîne. Dans l'exemple ci-dessus, la sous-chaîne "tout" commence à la position 8 de la chaîne.

La méthode `slice()` renvoie une portion de la chaîne en spécifiant les index de début et de fin. Dans l'exemple ci-dessus, la portion de la chaîne entre les index 3 et 9 (inclus) est "jour t".

Il existe de nombreuses autres méthodes que vous pouvez utiliser pour manipuler des chaînes de caractères en JavaScript. Je vous encourage à explorer davantage pour en découvrir plus.


## Les tableaux

En JavaScript, les tableaux sont des objets qui permettent de stocker des valeurs de différents types, tels que des nombres, des chaînes de caractères, des booléens, des objets, etc. Les éléments d'un tableau sont identifiés par leur index, qui commence à zéro pour le premier élément.

Voici comment créer un tableau en JavaScript :

``` javascript
var monTableau = [valeur1, valeur2, valeur3];
```

Ou bien :
``` javascript
var monTableau = new Array(valeur1, valeur2, valeur3);

```

On peut également créer un tableau vide et y ajouter des éléments par la suite :

``` javascript
var monTableau = []; 
monTableau[0] = valeur1; 
monTableau[1] = valeur2; 
monTableau[2] = valeur3;
```

Les tableaux en JavaScript disposent de nombreuses méthodes pour manipuler les éléments. Voici quelques exemples :

-   Accéder à un élément : on peut accéder à un élément d'un tableau en utilisant son index :
``` javascript
var monTableau = ["valeur1", "valeur2", "valeur3"];
console.log(monTableau[0]); // affiche "valeur1"
```

Modifier un élément : on peut modifier la valeur d'un élément d'un tableau en utilisant son index :
``` javascript
const monTableau = ["valeur1", "valeur2", "valeur3"]; 
monTableau[1] = "nouvelleValeur"; 
console.log(monTableau); // affiche ["valeur1", "nouvelleValeur", "valeur3"]
```

Ajouter un élément : on peut ajouter un élément à un tableau en utilisant la méthode "push" :

``` javascript
var monTableau = ["valeur1", "valeur2", "valeur3"]; monTableau.push("nouvelleValeur"); 
console.log(monTableau); // affiche ["valeur1", "valeur2", "valeur3", "nouvelleValeur"]
```

Supprimer un élément : on peut supprimer un élément d'un tableau en utilisant la méthode "splice" :
``` javascript
var monTableau = ["valeur1", "valeur2", "valeur3"];
monTableau.splice(1, 1);
console.log(monTableau); // affiche ["valeur1", "valeur3"]
```

Parcourir un tableau : on peut parcourir les éléments d'un tableau en utilisant une boucle "for" ou "for...of" :

``` javascript
const monTableau = ["valeur1", "valeur2", "valeur3"]; 
for (var i = 0; i < monTableau.length; i++) { console.log(monTableau[i]); 
} // ou for (var element of monTableau) { console.log(element); }
```



## Structures de controle

 Les structures de contrôle sont des constructions syntaxiques dans un langage de programmation qui permettent de contrôler l'exécution du code. Elles permettent de spécifier l'ordre dans lequel les instructions sont exécutées et d'exécuter certaines instructions en fonction de certaines conditions ou répéter certaines instructions plusieurs fois. Les structures de contrôle sont essentielles pour la programmation car elles permettent de créer des programmes plus complexes et plus dynamiques.

 Les structures de contrôle sont importantes en programmation pour plusieurs raisons:
-   Elles permettent de contrôler l'exécution des instructions et d'adapter le comportement du programme en fonction des conditions rencontrées.
-   Elles permettent de répéter des instructions plusieurs fois sans avoir à les écrire à chaque fois, ce qui facilite la réutilisation du code et rend le programme plus efficace.
-   Elles permettent de structurer le code en organisant les instructions de manière logique et en les regroupant en blocs de code cohérents.
-   Elles permettent de rendre le code plus lisible et plus facile à maintenir en clarifiant l'intention du programmeur.

 Les deux structures de contrôle de base en JavaScript sont les instructions conditionnelles (ou conditions) et les boucles.



### Les instructions conditionnelles

Les instructions conditionnelles permettent de prendre des décisions en fonction de certaines conditions. Les instructions conditionnelles les plus courantes en JavaScript sont les instructions `if`, `else` et `else if`.

#### L'instruction if

L'instruction `if` permet de spécifier un bloc de code à exécuter si une condition est vraie. Voici un exemple :

``` javascript
let age = 25;

if (age >= 18) {
  console.log("Vous êtes majeur !");
}
```

Dans cet exemple, le bloc de code à l'intérieur de l'instruction `if` ne sera exécuté que si la condition `age >= 18` est vraie.

#### L'instruction else

L'instruction `else` permet de spécifier un bloc de code à exécuter si la condition de l'instruction `if` est fausse. Voici un exemple :

``` javascript
let age = 15;

if (age >= 18) {
  console.log("Vous êtes majeur !");
} else {
  console.log("Vous êtes mineur !");
}

```

Dans cet exemple, si la condition `age >= 18` est fausse, le bloc de code à l'intérieur de l'instruction `else` sera exécuté.

### L'instruction else if

L'instruction `else if` permet de spécifier une autre condition à vérifier si la condition de l'instruction `if` est fausse. Voici un exemple :
``` javascript
if (condition1) { 
	// instructions à exécuter si condition1 est vraie
} else if (condition2) { 
	// instructions à exécuter si condition1 est fausse et condition2
	// est vraie 
} else { 
	// instructions à exécuter si les deux conditions précédentes sont
	// fausses
}
```

### L'operateur ternaire

L'opérateur ternaire en JavaScript est une version abrégée de l'instruction "if/else". Il permet d'écrire une expression conditionnelle sur une seule ligne.

Voici la syntaxe de l'opérateur ternaire :
``` javascript
condition ? valeurSiVraie : valeurSiFausse;

```
Si la condition est vraie, l'opérateur ternaire renvoie la "valeurSiVraie", sinon il renvoie la "valeurSiFausse".

Par exemple, voici comment utiliser l'opérateur ternaire pour assigner une valeur différente à une variable selon qu'une condition est vraie ou fausse :

``` javascript
var age = 25;
var statut = (age >= 18) ? "majeur" : "mineur";
console.log(statut); // affiche "majeur"
```

Dans cet exemple, si la variable "age" est supérieure ou égale à 18, l'opérateur ternaire renvoie la valeur "majeur", sinon il renvoie la valeur "mineur". La valeur renvoyée est ensuite assignée à la variable "statut".

L'opérateur ternaire peut être utilisé pour des expressions plus complexes. Toutefois, il est recommandé de ne pas l'utiliser de manière abusive afin de maintenir la lisibilité du code.

### Les boucles 

Les boucles sont des structures de contrôle en JavaScript qui permettent de répéter des instructions plusieurs fois. Il existe plusieurs types de boucles, chacun ayant ses propres caractéristiques. Voici une explication pour chacune d'elles :

1.  **La boucle while** : La boucle while est utilisée pour répéter des instructions tant qu'une condition donnée est vraie. La syntaxe est la suivante :
``` javascript
while (condition) {
  // instructions à répéter
}
```
Les instructions situées entre les accolades sont répétées tant que la condition est vraie.

2.  **La boucle do...while** : La boucle do...while est similaire à la boucle while, sauf qu'elle s'exécute au moins une fois avant de vérifier la condition. La syntaxe est la suivante :
``` javascript
do {
  // instructions à répéter
} while (condition);
```

Les instructions situées entre les accolades sont répétées au moins une fois, puis répétées tant que la condition est vraie.

3.  **La boucle for** : La boucle for est utilisée pour répéter des instructions un nombre spécifié de fois. La syntaxe est la suivante :
``` javascript
for (initialisation; condition; incrémentation) {
  // instructions à répéter
}
```
La première instruction est exécutée avant la boucle, la deuxième instruction est la condition qui doit être vraie pour que la boucle continue à s'exécuter, la troisième instruction est exécutée à chaque fois que la boucle est répétée.

4.  **La boucle for...in** : La boucle for...in est utilisée pour parcourir les propriétés d'un objet. La syntaxe est la suivante :
``` javascript
for (variable in objet) {
  // instructions à répéter
}
```
La variable prendra successivement la valeur de chaque propriété de l'objet.

5.  **La boucle for...of** : La boucle for...of est utilisée pour parcourir les éléments d'un tableau, d'un ensemble ou d'une chaîne de caractères. La syntaxe est la suivante :
``` javascript
for (variable of iterable) { // instructions à répéter }
```
La variable prendra successivement la valeur de chaque élément de l'itérable.

Il est important de bien choisir la boucle la mieux adaptée pour chaque situation afin d'éviter des erreurs de logique ou d'efficacité de code.



## Les fonctions

Une fonction en JavaScript est un bloc de code qui peut être appelé et exécuté plusieurs fois à partir de différents endroits dans le programme. Elle peut prendre des arguments et renvoyer une valeur ou un résultat de traitement. Les fonctions en JavaScript sont considérées comme des objets de première classe, ce qui signifie qu'elles peuvent être passées en tant que paramètres, affectées à des variables, retournées à partir d'autres fonctions et stockées dans des structures de données.

 Les fonctions sont importantes en programmation car elles permettent de réutiliser du code, d'éviter la duplication de code et de rendre le code plus modulaire et plus facile à maintenir. Les fonctions peuvent également aider à structurer le code en le divisant en blocs logiques et en rendant les algorithmes plus compréhensibles. En outre, les fonctions peuvent être utilisées pour rendre le code plus évolutif en permettant de modifier le comportement de la fonction sans avoir à modifier le reste du code.


La syntaxe de base d'une fonction en JavaScript est la suivante :
``` javascript
function nom_de_la_fonction(param1, param2, ...) {
	// instructions
	return resultat;
}
```


 La déclaration de fonction commence par le mot-clé `function` suivi du nom de la fonction, puis d'une paire de parenthèses qui contiennent les paramètres de la fonction. Si la fonction ne prend pas de paramètres, les parenthèses restent vides.
 Les instructions à exécuter dans la fonction sont contenues dans un bloc de code entre des accolades `{}`.
La fonction peut renvoyer une valeur ou un résultat de traitement à l'aide du mot-clé `return`. Si la fonction ne renvoie rien, la valeur `undefined` est renvoyée par défaut.



### Les différentes façons de définir une fonction en javascript

**A. La déclaration de fonction** 
La déclaration de fonction est la façon la plus courante de définir une fonction en JavaScript. Elle se fait en utilisant le mot-clé `function`, suivi du nom de la fonction et d'une paire de parenthèses pour les paramètres éventuels. Voici un exemple de déclaration de fonction :

``` javascript
function addition(a, b) { 
	return a + b; 
}
```

**B. L'expression de fonction** 
L'expression de fonction est une autre façon de définir une fonction en JavaScript. Elle consiste à affecter une fonction anonyme à une variable. Voici un exemple d'expression de fonction :

``` javascript
let multiplication = function(a, b) {
  return a * b;
}
```


**C. Les fonctions fléchées**
Les fonctions fléchées sont une autre façon de définir des fonctions en JavaScript. Elles ont été introduites dans ECMAScript 6 pour rendre la syntaxe des fonctions plus concise. Les fonctions fléchées ne nécessitent pas le mot-clé `function` et utilisent une syntaxe différente pour définir les paramètres et le corps de la fonction. Voici un exemple de fonction fléchée :

``` javascript
let soustraction = (a, b) => a - b;
```

Dans cet exemple, les paramètres sont définis entre des parenthèses et la flèche `=>` indique que la fonction renvoie l'expression suivante. Si la fonction contient plusieurs instructions, elles doivent être entourées d'accolades, comme dans cette exemple :

``` javascript
let division = (a, b) => {
  if (b === 0) {
    return "Impossible de diviser par zéro";
  } else {
    return a / b;
  }
};

```
