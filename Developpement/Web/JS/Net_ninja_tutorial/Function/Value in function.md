Pour passer des [[Types|valeurs]] dans une fonction il faut les mettre en option de l'appel et en paramètre de la fonction :
```js
// arguments & parameters  
const speak = function(name){  
    console.log(`hello ${name}!`);  
};  
  
speak('shaun');

//log : 
//hello shaun!
```

L'ordre des option est importante :
```js
const speak = function(name, time){  
    console.log(`good ${time}, ${name}!`);  
};  
  
speak('morning', 'mario'); 

// log :
// good mario, morning!
```

On peut également donner une valeur par défaut à un paramètre :
```js
const speak = function(name = 'luigi', time = 'night'){  
    console.log(`good ${time}, ${name}!`);  
};  
    
speak();  // good night, luigi!
```

Mais lorsque l'on passe des options sur l'appel de fonction, la valeur par défaut va être écrasé :
```js
const speak = function(name = 'luigi', time = 'night'){  
    console.log(`good ${time}, ${name}!`);  
};  
  
speak('shaun'); // good night, shaun!
```