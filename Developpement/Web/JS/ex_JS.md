# Java Script

## Les variables 
Pour instancier une variable, on utilise : 
```js
var maVariable = "bonjour";
```

Il est possible de changer la valeur de la variable :
```js
maVariable = "au revoir";
```

Utiliser `var` est déconseillé car il est ancien, aujourd'hui il est conseillé d'utiliser let et const :
```js
let age = 30;
age = 31 //changera la la valeur que une variable let est modifiable

const age=30;
age=30; //affichera une erreur car const est une constante et il n'est pas modifiable
```

Pour instancier une variable de type String il est possible d'utiliser des simple quotes, des double quotes et des backtick
```js
const variable1 = 'a string';
const variable2 = "another string";
const variable3 = `yet another string`;
```

Il est possible de mettre des double quotes dans des simples quotes, inversement et également avec des backtick :
```js
const variable1 = "bonjour je suis 'david'";
```

Il est possible de concaténéer plusieurs variable :
```js
const variable1 = 'a string';
const variable2 = "another string";

const concacatString = variable1 +' '+ variable2;
console.log(concactString); //affichera "a string another string"
```

```js
const variable3 = `yet another string`;

const concactMethod = variable3.concact(', that\'s so great'); // l'anti slash permet de forcer l'affichage de ' en caractères
console.log(concactMethod);// affichera "yet another string, that's so great"
```
### modification

Pour modifier une variable on peut utiliser plusieurs paramètres, par exemple :
``` js
let message = "Bonjour tout le monde !";
console.log(message.toLowerCase()); // bonjour tout le monde !
console.log(message.toUpperCase()); // BONJOUR TOUT LE MONDE !
console.log(message.slice(3, 9)); // jour t
```

## Les types de données

Il existe plusieurs types de variable en JS :
	- les chaines de caractères (string)
	- les nombres (number)
	- les booléens (boolean)
	- les tableaux (array)
	- les objets (object)

Pour determiner les type de données on utilise l'opérateur `typeof`
``` js
var maVariable = "bonjour";
consol.log(typeof maVariable); //affichera "string" dans la console

var maVariable = 30;
consol.log(typeof maVariable); //affichera "number" dans la console
```

## Opérateurs Mathématique

Il est possible d'utiliser des opérateurs pour executer des calculs :
	- `+` pour effectuer des addition
	- `-` pour effectuer des soustraction
	- `*` pour effectuer des multiplications
	- `/` pour effectuer des division
	- `%` pour effectuer es modulo

```js
var maVariable1 = 30;
var maVariable2 = 31;

var resultat = maVariable1 + maVaraible2;
console.log(resultat); // affichera 61
```



### length
la commande `.length` permet de retournera la longueur de l'objet : 
```js
const variable3 = `yet another string`;  
const length1 = variable3.length;  
console.log(length1); // affichera "18"
```



## tableau
Pour créer des tableau il est possible d'utiliser des crochet ou bien array :
``` js
var monTableau = [valeur1, valeur2, Valeur3]; //il est préférable d'utiliser cette methode
ou
var monTableau = new array(valeur1, valeur2, valeur3);
```

Il est également possible de créer un tableau vide et d'ajouter des éléments par la suite
```js
var monTableau = [];
monTableau[0] = valeur1;
monTableau[1] = valeur2;
monTableau[2] = valeur3;
```

Pour modifier un tableau il suffit de réécrire la valeur :
```js
var monTableau = [valeur1, valeur2, Valeur3];
monTableau[1] = maValeur;
```
Pour afficher un éléments du tableau :
```js
var monTableau = [valeur1, valeur2, Valeur3];
monTableau[1] = maValeur;
console.log(montableau(0)) // valeur1
```

Pour afficher chaque éléments d'un tablea on utilise une boucle :
```js
const myArray = [1, 2, 3, 4, 5, 6, 7]

for (let index=0 ; index < myArray.length ; index++){
	const element = myArray[index];
	console.log(element)
}
```

## Les condition


### If Else
les condition if et else d'executer une instruction selon plusieurs cas:
```js
let age=15;

if(age>=18){
	console.log("vous etes majeur !")
}
else{
	console.log("vous etes mineur!")
}
```

## Les boucles

Pour utiliser des boucle il existe plusieur manière

### while
while permet de répeter une instruction tant que la condition est vrai :
```js
while(condition) {
	//instruction a repeter
}
```

### for
for permet d'xecuter des instruction en fonction d'une condition :
``` js
for (condition){
	instructin a repeter
}
```

### for of
permet de parcourir les éléments d'un tableau :
```js
for (variable of iterbale){
	instruction
}
```

## Les objets
pour instancier un objet :
```js
const someStudent = {
	lastname: 'GAILLETON',
	firstname: 'David',
	age: 18,
	hobbies: ['computer science', 'cooking', 'clarinet'],
	beauty: 'really handsome',
}

console.log(someStudent.firstname); //David
console.log(someStudent.age); //18
```

## Les Fonctions

Les fonctions permettent de créer une variable contenant des instruction :
```js
// définiton d'une fonction qui retourne une soustraction
function soustraire(a, b){
	return a - b;
}
//execution de la fonction en spécifiant les paramètres
const resultat = soustraire(4, 5);
console.log(resultat); //-1
```

La nouvelle façon d'utiliser une fonction est :
```js
//déconseillé mais il est possible d'écrire sur une seul ligne
const soustraire = (a, b) => a - b;

ou
// nouvelle méthode hautement conseillé
const soustraire = (a, b) => { 
	return a - b;
}
```


