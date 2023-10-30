Une `arrow function` est une façon de déclarer une fonction plus courte, elle porte ce nom car elle contient le signe ` =>` 
Il est conseillé d'utiliser cette façon :
```js
const functionName = (parametre1, parametre2) => {
	// fonction
}
```
lorsqu'il n'y a qu'un paramètre, il n'est pas obligatoire de mettre les parenthèse :
```js
const functionName = parametre => {
	// fonction
}
```
lorsque'il n'y a pas de parametre, on met des parentheses vide :
```js
const functionName = () => {
	// fonction
}
```

Pour un fonction s'écrivant sur 1 seul ligne qui contient `return`, on peut raccourcir la fonction sur une seul ligne :
```js
const functionName = radius => 3.14 * radius**2;
```
