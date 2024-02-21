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
Une variable peut être définie à l'intérieur d'une boucle ou d'une condition.
Si elle est instancié dans un boucle ou une condition elle ne peut pas être le en dehors :
```js
let age = 30;  
  
if(true){  
    let age = 40;  
    console.log('inside 1st code block:', age);  
  
    if(true){  
  
        let age = 50;  
        console.log('inside 2nd code block:', age);  
  
    }  
  
}  
  
console.log('outside code block:', age);

// log :
// inside 1st code block: 40 shaun
// inside 2nd code block: 50 shaun
// outside code block: 30
```

Si on essaie de lire une variable encapsulé à l'extérieur de celle si, la console retournera une erreur :
```js
let age = 30;  
  
if(true){  
  
    // age = 40;  
    let age = 40;  
    let name = 'shaun';  
    console.log('inside 1st code block:', age, name);  
  
    if(true){  
  
        let age = 50;  
        console.log('inside 2nd code block:', age, name);  
  
    }  
  
}  
  
console.log('outside code block:', age);
```
log :
```bash
inside 1st code block: 40 shaun
inside 2nd code block: 50 shaun
C:\Users\David\SynologyDrive\Documents\Developpement\Cours\Web\JS\Net-ninja-courses\TestEnv\sandbox.js:20
console.log('outside code block:', age, name);
                                        ^

ReferenceError: name is not defined
    at Object.<anonymous> (C:\Users\David\SynologyDrive\Documents\Developpement\Cours\Web\JS\Net-ninja-courses\TestEnv\sandbox.js:20:41)
    at Module._compile (node:internal/modules/cjs/loader:1241:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1295:10)
    at Module.load (node:internal/modules/cjs/loader:1091:32)
    at Module._load (node:internal/modules/cjs/loader:938:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:83:12)
    at node:internal/main/run_main_module:23:47
```