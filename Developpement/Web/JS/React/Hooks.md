# Les Hooks

Les hooks sont des fonctions de la bibliothèque [[React]] commençant pas `use`.

## Regles essentiel

- Les hooks ne peuvent pas etre appelees qu'au niveau le plus haut d'un composant. 
- Les hooks ne peuvent pas etre appeles au sein d'event handler.
- un hook ne peut pas etre appelee conditionnellement.
- Les hooks ne peuvent etre appelees qu'a l'interieur de composant fonction et pas dans un composant class.

## Les hooks principales

### useState - hook d'etat

Il est possible de forcer une variable d'état en utilisant les chevron (`<string>`) :
```tsx
const [Visible, setVisible] = useState<boolean>(true);
```

### useEffect

Le hook useEffeect permet de gerer les effets de bords en React (side effect).
Une application React est une fonction qui affiche du contenu a un endroit tres precus du DOM (un element HTML dont l'ID est root...).
La syntaxe est la suivante : 
```tsx
function unComponent() {
    useEffect(() => {
            () => {}
        console.log('passage par le hook useEffect');
        return () => {}
    },
        []
    )
}
```
Ce code contient 2 parametre, le premier est une fonction. Le second est un tableau de dependences, si ce dernier est vide, la fonction passe en premier parametre du hook useEffect est executable a chaque rendu du composant a l'ecran.


### useContext



#### createContext

### useReducer