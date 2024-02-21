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