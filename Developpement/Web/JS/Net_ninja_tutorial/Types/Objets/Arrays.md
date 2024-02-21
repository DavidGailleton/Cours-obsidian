Les tableau est un Objet permettant de contenire plusieurs valeurs ou fonction.
Les tableaux se définisse par des `[]`

Par exemple, un tableau de strings :
```js
let result = ['shaun', 'ryu', 'chun-li'];
```

Il est possible lister tout les éléments du tableau :
```js
console.log(result);
// "shaun", "ryu", "chun-li"
```

Pour sélectionner un seul élément du tableau on utilise `[]`
```js
console.log(result[1]);
// ryu
```

Il est possible de remplacer une valeur d'un tableau en sélectionnant son emplacement :
```js
result[1] = 'ken';
console.log(result[1]);
// ken
```


## Propriété
Certaines propriété fonctionnes également sur les tableaux :
```js
console.log(result.length)
// 3
```

## Methodes
### `join()`
La méthode `join` permet d'écrire dans la console un string avec les élément du tableau lié par un élément choisie :
```js
console.log(result.join(','));
// shaun,ryu,chun-li
```

### `indexOf()`
La méthode `indexOf` permet de trouver la position d'un élément dans un tableau :
```js
console.log(result.indexOf('ryu'));
// 1
```

### `concat()`
LA méthode `concat` permet de lié plusieurs tableau :
```js
console.log(result.concat(['ken', 'ragnar']));
// [ 'shaun', 'ryu', 'chun-li', 'ken', 'ragnar' ]
```

### `push()`
La méthode push permet d'ajouter un nouvelle valeur à un tableau :
```js
let ninjas = ['shaun', 'ryu', 'chun-li'];  
let result = ninjas.push('ken');  
console.log(result);  // 4
console.log(ninjas); // ["shaun", "ryu", "chun-li", "ken"]
```

### `pop()`
La méthode pop permet de supprimer un élément du tableau :
```js
let ninjas = ['shaun', 'ryu', 'chun-li'];  
let result = ninjas.pop(2);  
console.log(result);  // chun-li
console.log(ninjas); // [ 'shaun', 'ryu' ]
```

