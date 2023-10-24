En [[JS]] il est possible de créer des template.

Le template des exemple :
```js
const title = 'Best reads of 2019';
const author = 'Mario';
const likes = 30;
```
## Concatenation way
Il est possible de créer un template via un concatenation simpla :
```js
let result = 'The blog called ' + title + ' by ' + author + ' has ' + likes + ' likes';
```

## Template string way
Un template string est toujours entouré de backticks.
```js
let result = `The blog called ${title} by ${author} has ${likes} likes`
```

## HTML templates
Il est possible de créer des templates de code HTML :
```js
let html = `
	<h2>${title}</h2>
	<p>By ${author}</p>
	<span>This blog has ${likes} likes</span>
`;
```

