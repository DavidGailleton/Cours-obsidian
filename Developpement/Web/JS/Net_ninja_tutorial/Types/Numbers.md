## Opérations
### Opérateurs
Il y a différents opérateurs permettant de modifier les valeurs des nombres en [[JS]]
- + : addition
- - : soustraction
- * : multiplication
- / : division
-  ** : puissance
- % : modulo

### Ordres des opération
Les opérations s'éxécute avec l'ordre B I D M A S :
- B: bracket (parenthèse)
- I : Indecise (puissance)
- D : Division
- M : Multiplication
- A : Adition
- S : Subtraction (Soustraction)

### Shorthand Notation
Il y quelque raccourcis dans les opérateurs :
#### Addition
`++` ou `--` est équivalent à `+ 1` ou `- 1`
```js
let likes = 10;

likes = likes + 1;
//is equal to
likes++;

likes = likes - 1;
//is equal to
likes--;
```

Pour faire une addition avec un plus grand nombre, on utilise `+=`
```js
likes += 10;
// equal 20
```
 Ce dernier fonction avec les autres opérateur
 ```js
likes -= 5;
// equal 5

likes /= 2;
// equal 5

likes *= 4;
// equal 40
```

## Special value
### NaN : Not a Number
La valeur NaN est définie lorsque le code essaie de faire un calcule impossible :
```js
let result = 6 * "hello";
// result is equal to NaN
```

