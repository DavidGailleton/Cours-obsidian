## Break
`break;` permet de complètement arrêter un boucle :

```js
const scores = [50, 25, 0, 30, 100, 20, 10];  
  
for(let i = 0; i < scores.length; i++){  
    console.log('your score:', scores[i]);  
  
    if(scores[i] === 100){  
        console.log('congrats, you got the top score!');  
        break;  
    }  
  
}

// log :
// your score: 50
// your score: 25
// your score: 0
// your score: 30
// your score: 100
// congrats, you got the top score!
```
## Continue

```js
const scores = [50, 25, 0, 30, 100, 20, 10];

for(let i = 0; i < scores.length; i++){

  if(scores[i] === 0){
    continue;
  } // bypass tout les 0

  console.log('your score:', scores[i]);

  if(scores[i] === 100){
    console.log('congrats, you got the top score!');
    break;
  }

}

// log:
// your score: 50
// your score: 25
// your score: 30
// your score: 100
// congrats, you got the top score!
```

