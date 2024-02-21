## Strings
Les chaines de caractères peuvent être définit par des simple quotes, des doubles quotes ou des back ticks :

```js
console.log('Hello, world');
```

```js
let chaineDeCaractères = "Hello, world";
```

```js
const email = `Hello, world`;
```

## Concaténation

```js
let firstName = 'Jhon';
let secondName = 'Dow';

let fullName = firstName + '' + lastName
// fullName sera égal à "Jhon Dow"

let fullName = "Hello" + 6 + 'guys'
// fullName sera égal à "Hello 6 guys"
```

## Getting characters

```js
console.log(fullName[0]);
// retournera "J" car la première position d'une chaine de caractere est 0
```

## Propriété `length`
```js
console.log(fullName.length);
// sera égale à 8
```

## Méthodes
Il y a de nombreuse fonction en [[JS]] que l'on appel `Methods`

### `toUpperCase()`
Cette méthodes permet de mettre tous le caractères en majuscule
```js
console.log(fullName.toUpperCase());
// retournera "JHON DOW"
```

### `toLowerCase()
Cette méthodes permet de mettre tous le caractères en minuscule
```js
let nameLower = fullName.toLowerCase();
// retournera 'jhon dow'
```

### `indexOf()`
La méthode `indexOf()` permet de trouver la position d'un caractère
```js
let email = "jhon.dow@licdac.fr";
let result = email.indexOf("@");
// retournera 8
```

#### `lastIndexOf()`
La méthode `lastIndexOf()` permet de trouver la dernière position d'un caractère spécifique :
```js
let test = "Lorem Ipsum"
let lastIndex = test.lastIndexOf("m");
// retournera 10
```

### `slice()`
La méthode `slice()` permet de découper une chaine de caractère pour garder seulement les caractères d'un plage donnée :
```js
let theSlice = fullName.slice(0, 6);
// Jhon D
```

### `substr()`
LA méthode `substr` ressemble à la méthode [[#`slice()`]]  à la différence que le 2eme argument vas correspondre au nombre de caractère voulu et non à la position du caractère :
```js
let result = email.substr(2, 7);
// "on.dow@"
```

### `replace()`
La méthode `replace` va prendre en argument 2 option, le 1er est le caractère à remplacer et le second est le caractère remplacent. Cette méthodes va remplacer le premier caractère de la chaine correspondant à la première option :
```js
let result = email.replace('c', 'k');
// "jhon.dow@likdac.fr"
```

