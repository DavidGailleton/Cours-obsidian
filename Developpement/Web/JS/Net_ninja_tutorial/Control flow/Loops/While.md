Un boucle `while` ne prend qu'un seul paramètre, la condition d'éxecution
```js
let i = 0;
while(i < 5){
	console.log(i);
	i++;
}
// log:
// 0
// 1
// 2
// 3
// 4
```

```js
let names = ['mario', 'luigi', 'toad'];  

let i =0;
while(i < names.length){
    console.log(names[i]);
    i++
}
// log:
// mario
// luigi
// toad
```