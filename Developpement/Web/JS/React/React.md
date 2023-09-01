React est une bibliothèque open source qui permet la construction interface graphique avec [[HTML]], [[CSS]] et [[JS]].

Sommaire :
- Comprendre les avantages apportés par React
- Découvrir les **JSX** (JS-XML) qui est une extension de JS
- Créer des **composants**
- Comprendre les imports et les exports
- Utiliser **props**
- Utiliser le State
- Utiliser les events en React

Javascript permet de manipuler le DOM : c'est la représentation 'objet' des éléments HTML qui constitue un page web. Autrement dit, c'est une interface qui permet d’interagir avec la structure des pages web.

React utilise un DOM virtuel pour afficher ses composants (virtual DOM, Shadow DOM), car manipuler le DOM directement peut être très coûteux.

```tsx
function app() {
	return (
		<div className="App"></div> //class devient className en JSX
	)
}
```

React n'est pas directement éxécuter par les navigateurs web. La conversion de JSX en JS et HTML pour le web s'appel la transpilation.

Une app React est composé d'un fichier index.js :
```tsx
import { StrictMode } from "react";

import { createRoot } from "react-dom/client";

  

import App from "./App";

  

const rootElement = document.getElementById("root");

const root = createRoot(rootElement);

  

root.render(

<StrictMode>

<App />

</StrictMode>

);
```

Root est l'app React. ??????

## Imports Exports

Les imports et exports permettent de structurerles fichiers JS en modules.
Par defaut JS execute ce qu'on appelle la 'global scope' . Le contenue du code provenant d'un fichier est automatiquement disponible au sein d'un autre fichier.
Le fichiers ont pour extension : .js .ts .jsx .tsx 

On peut considérer qu'un fichier js est un module des lors qu'il contient un 'export' :
```js
function myFuncA () {
	
}
function myFuncB () {

}
function myFuncC () {

}
export {myFuncA, myFuncB, myFuncC};
```

On peut ensuite l'importer a partir d'un autre fichier en utilisant 'import' :
```js
import {} from './export'

myFunc();

```

![import-export-cheatsheet.jpg](img%2Fimport-export-cheatsheet.jpg)


## Initialisation d'un projet React

Pour initialiser un projet React on vas utiliser 'Vite' via cette commande :
```shell
npm create vite my-react-app -- --template react
```

## Les `Components`

Il est possible d'importer des templates dans d'autres templates :
```jsx
//./component/MyComponent.jsx
function myComponent() {
	return(
			<>
				<h1>Hello World !</h1>
			</>
	)
}

//const myComponent = () => <h1>Hello World !</h1> Autre manière d'utiliser un fonction

export default myComponent
```
```jsx
//./App.jsx
import MyComponent from "./components/MyComponent.jsx";

function App() {
  const [count, setCount] = useState(0)

  return (
    <>
      <MyComponent />
    </>
  )
}

export default App
```

### Les Props

Les props sont un parametre optionnel qu'on peut passer a un composant React.
Elles constituent un objet qui contient notemment des propiétés que l'on peut choisir.
 ```jsx
function myComponent(props) {
    console.log({props})
    return(
        <>
            <h1>{props.uneProp}</h1>
        </>
    )
}
```
Les paramètre de 'uneProp' sont initialisé dans le composant parent :
```jsx
function App() {
	const [count, setCount] = useState(0)

	return (
			<>
				<MyComponent uneProp="test" />
			</>
	)
}
```
#### La prop 'Childrens'

La prop `children` permet d'afficher toutes les balises enfant du composant parent

```jsx
import MyComponent from "./MyComponent";

function App() {
	const [count, setCount] = useState(0)

	return (
			<>
				<MyComponent> 
                	<div>test</div>
                </MyComponent>
			</>
	)
}
```
```jsx
export default function MyComponent({children}) { 
	return(
			<>
				{children}
			</>
	)
}
```
Dans ce cas la div test sera afficher seulement si {children} est ajouté dans MyComponent.jsx

### Le state

L'etat d'un composant designe une variable speciale qui contient des informations sur le contenu actuel du composant. Par exemple, un composant peut être en état d'erreur ou de chargement.
Un changement de cet état va entraîner ce qu'on appelle comunement un : 're-ender'

## Condition ternaire
En JSX il n'est pas possible d'écrire des condition sur plusieurs ligne, on utilise donc des condition ternaire :
```tsx
type === 'warning' ? 'warning': 'information'

//equivalente a
if (type === "warning") {
	return "Warning";
} else {
	return "Information";
}
```



## Provider

Garde en mémoire des variables (ex: formulaires sur plusieurs pages, panier)

-> utile quand on passe les memes props sur plusieurs fichiers
permet de mettre à jour props sur autres fichiers

créer fichier context.tsx
créer contexte avec React.createContext()
exporter component qui retourne une balise
`<context.Provider value={}> {children} </>`