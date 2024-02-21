Une fonction est un block de code pouvant être appelé n'importe ou, comme une variable :
```js
// function déclaration
function myFunction(){
	console.log('hello world')
}

myFunction();

// log :
// hello world
```

## `function expression`
Par défault, les fonction sont automatique lu en priorité par le programme ce qui leurs permette d'être lu n'importe ou. Cependant la `function expression` ne peut être lu seulement après avoir avoir été déclaré :
```js
speak(); // speak is not defined
greet(); // hello there

function greet(){  
    console.log('hello there');  
}  
// function expression
const speak = function(){  
    console.log('good day!');  
};
speak(); // good day!
```