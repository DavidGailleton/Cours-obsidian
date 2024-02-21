La méthode switch permet d'éviter d'utiliser des [[Else and Else if statement|else if]] à répétition en exécutant une fonction en fonction d'un cas précis :

Avec else if :
```js
const grade = 'D';

if(grade === 'A'){  
  console.log('you got a A!');
} else if(grade === 'B'){  
  console.log('you got a B!');
} else if(grade === 'C'){  
  console.log('you got a C!');
} else if(grade === 'D'){  
  console.log('you got a D!');
} else if(grade === 'E'){  
  console.log('you got a E!');
} else {  
  console.log('not a valid grade');
}
```

Avec switch case :
```js
const grade = 'D';  
  
switch(grade){  
    case 'A':  
        console.log('you got an A!');  
        break;  
    case 'B':  
        console.log('you got a B!');  
        break;  
    case 'C':  
        console.log('you got a C!');  
        break;  
    case 'D':  
        console.log('you got a D!');  
        break;  
    case 'E':  
        console.log('you got an E!');  
        break;  
    default:  // default est la condition qui sera exécuter si aucun cas ne correspond
			  // à l'option demandé
        console.log('not a valid grade');  
}
```

Dans ce code on utilise la méthode [[Break & Continue|Break]] pour que le programme ne lit pas les autre cas si il trouve un cas valide, c'est un optimisation.