Le but principal d'une fonction est de retourner une valeur, pour faire ceci on utilise `return` :
```js
const calcArea = function(radius){  
    let area = 3.14 * radius**2;  
    return area;  
    // or
    // return = 3.14 * radius**2;
}  
  
const area = calcArea(5);  
console.log('area is:', area); // area is: 78.5
```