Dans un boucle `for`, il y a 3 options :
1. Initialise une valeur
2. Donne une condition à l'exécution de la boucle. Si la condition retourne true, alors la boucle est éxécuté
3. La troisième option est un argument qui sera exécuter à la fin de chaque boucle

```js
for(let i = 0; i < 5; i++){  
      console.log(i)
}

// log:
// 0
// 1
// 2
// 3
// 4

```

Cette méthode est surtout utilisé pour trouvé un valeur dans une [[Base de données]] ou un [[Arrays|Tableau]] :
```js
let names = ['mario', 'luigi', 'toad'];  
  
for (let i = 0; i < names.length; i++){  
    console.log(names[i])  
}
// log:
// mario
// luigi
// toad
```

On peut également utiliser du code html :
```js
let names = ['mario', 'luigi', 'toad'];  
  
for (let i = 0; i < names.length; i++){  
    let html = `<div>${names[i]}</div>`  
}
```
