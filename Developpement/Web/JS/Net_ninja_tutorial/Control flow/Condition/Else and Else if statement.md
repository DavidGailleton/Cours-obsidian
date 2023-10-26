Si une condition [[If statement|if]] n'est pas respecté, il est possible d'exécuter une autre fonction avec `else` ou `else if` :
```js
const password = '@dm1n'

if(password.length >= 8){
	console.log('password is long enough')
} else {
	console.log('password is not long enough')
}
```

```js
const password = '@dm1n'

if(password.length >= 12){
	console.log('that password is might strong')
} else if(password.length >= 8){
	console.log('password is long enough')
} else {
	console.log('password is not long enough')
}
```