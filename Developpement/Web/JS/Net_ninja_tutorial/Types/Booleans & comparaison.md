Une valeur booleen est une valeur pouvant être égal soit à **true** soit à **false** :

## Méthodes
Il y à des méthodes permettant de retourner un booleen
### `includes()`
La méthode `includes` permet de vérifier si un élément contient l'élément en option :
```js
let email = 'test@test.fr';  
let result = email.includes('@');  
console.log(result); // true
```

```js
let names = ['mario', 'luigi', 'toad'];  
let result = names.includes('luigi');  
console.log(result); // true 
```

## opérateur de comparaison

### Numbers

avec le signe `'=='` on peut vérifier si une valeur est égal à une autre, elle retournera un booleen :
```js
let age = 25;
console.log(age == 25) // true
console.log(age == 40) // false
```

On peut vérifier si une valeur n'est pas égal à une autre avec la signe `'!='` :
```js
let age = 25;
console.log(age != 25) // false
console.log(age != 40) // true
```

ont peut également le faire avec d'autre opérateurs
```js
let age = 25;
console.log(age < 25) // false
console.log(age > 20) // true
console.log(age <= 40) // true
console.log(age >= 40) // false
```

### Strings
Il est également possible d'utiliser les comparaison avec des chaines de caracteres
```js
let name = 'jhon'
console.log(name == 'jhon') // true
console.log(name == 'Jhon') // false
```

Les lettre ont des valeurs implicite :
![[d439b6003af33a87caba06e5c15c10385243b57d.jpg]]

On peut donc les comparer :
```js
let name = 'jhon'
console.log(name < 'Jhon') // false
console.log(name > 'Jhon') // true
```

## Loose vs Strict comparaison

### Loose
En **loose** comparaison, la type de valeur n'a pas d'importance et peuvent être égal :
```js
let age = 25;
console.log(age == 25); // true
console.log(age == '25'); // true
```

### Strict
En comparaison, la méthode **Loose** vas prendre en compte le type de valeur :
```js
let age = 25;
console.log(age === 25); // true
console.log(age === '25'); // false
console.log(age !== 25); // false
console.log(age !== '25'); // true
```

Il est conseillé d'utilisé les comparaison Strict car il permet d'éviter les effets de bord