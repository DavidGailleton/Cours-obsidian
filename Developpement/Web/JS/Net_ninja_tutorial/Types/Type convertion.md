Il est possible de convertire une valeur en une autre

## [[Numbers]]
Par exemple pour convertire un string en nombre :
```js
let score = '100';
score = Number(score); 
console.log(score, typeOf score); // 100 "number"
```

Il est impossible de convertir une lettre en nombre :
```js
let score = 'hello';
score = Number(score); 
console.log(score); // NaN
```

## [[Booleans & comparaison|Booleen]]
### Number
Il est possible de convertire une valeur en boolean.
Pour les nombre, tout ce qui n'est pas **égal à 0** est égal a **true** :
```js
let score = '100';
score = Boolean(score); 
console.log(score, typeOf score); // true "boolean"
```

```js
let score = '0';
score = Boolean(score); 
console.log(score, typeOf score); // false "boolean"
```

### [[Strings]]
Pour les chaines de caractères, seulement les chaines vide sont égal à false :
```js
let score = 'hello';
score = Boolean(score); 
console.log(score, typeOf score); // true "boolean"
```

```js
let score = '';
score = Boolean(score); 
console.log(score, typeOf score); // false "boolean"
```

