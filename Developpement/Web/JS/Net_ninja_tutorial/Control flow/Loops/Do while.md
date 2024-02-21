la boucle `do while` est une sorte d'extension à [[While]].
Il permet d'obligatoirement exécuter au moins une fois le code sans regarder la condition.
Il est écrit d'un manière différente :

```js
let i = 0;

do {
	console.log(i);
	i++;
} while(i < 5);
// log:
// 0
// 1
// 2
// 3
// 4
```