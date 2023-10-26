Le block scope est la plage qu'une [[Variable_and_Constant|variable]] peut atteindre.
## Globale
Elle peut être globale, c'est a dire être appelé à n'importe quel endroit du code :
```js
let age = 30;  

let age = 50; // retourne une erreur
  
if(true){   
    console.log('inside 1st code block:', age);    
}  
  
console.log('outside code block:', age);
```

## Encapsulé