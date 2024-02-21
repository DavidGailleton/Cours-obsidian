## AND `&&`
L'[[a_faire/Opérateur logique|Opérateur logique]] AND s'écrit de la manière suivante en JS : `&&`
```js
const password = '@dm1n'

if(password.length >= 12 && password.includes('@') ){
	console.log('that password is might strong')
}
```

## OR `||`
L'[[a_faire/Opérateur logique|Opérateur logique]] OR s'écrit de la manière suivant en JS : `||` 
```js
const password = '@dm1n'

if(password.length >= 12 || ){
	console.log('that password is might strong')
} else if (password.length >= 8 || possword.includes('@')){
	console.log('that password is OK')
```

## NOT `!`
Le signe `!` inverse la condition d'exécution d'une fonction :
```js
let user = false;

if (!user){
	console.log('user is false')
}
// log:
// user is false
```

```js
let user = true;

if (!user){
	console.log('user is false')
}
// log:
// 
```