
## Elements de base

### `<html>`
L'element `<html>` est l'element racine des pages HTML

### `<head>`

Il contient des proprietes essentielles pour les pages web.
Chacune de ces proprietes est renseigne avec des elements enfants.

### `<body>`

Il contient l'ensemble des éléments visible sur la page web

```html
<html>
	<head>
	</head>

	<body>
	</body>
</html>
```

## Elements commun
### `<div>`

L’élément ``<div>`` est un des conteneurs les plus anciens du HTML. Il permet de créer une division structurelle dans la page. 
Dans ces divisions, nous pouvons placer n’importe quel contenu et même d’autres conteneurs comme d’autres divisions `<div>`, des paragraphes, des listes… 
Ces divisions permettaient d’effectuer des mises en page à l’aide de conteneurs "neutres", c’est à dire sans contenu sémantique défini.

**Voire les éléments [[Sémantique]] pouvant remplacer `div`**

### `<span>` 

L’élément `<span>` est souvent utilisé, par exemple, pour avoir une division au sein d’un paragraphe de texte. 
Ceci est très pratique pour mettre en forme de manière particulière du texte dans un texte formaté d’une autre manière.

### Les listes

#### Liste non ordonnée
``` html
<ul>
    <li>lorem</li>
    <li>ipsum</li>
    <li>foo bar</li>
</ul>
```
<ul>
    <li>lorem</li>
    <li>ipsum</li>
    <li>foo bar</li>
</ul>
#### Liste  ordonnée
``` html
<ol start="4" type="I" >
    <li>lorem</li>
    <li>ipsum</li>
    <li>foo bar</li>
</ol>
```
<ol start="4" type="I" >
    <li>lorem</li>
    <li>ipsum</li>
    <li>foo bar</li>
</ol>


### Les balises titres
#### `<title>`
L'élément `<title>` est toujours utilisé au sein de l'élément [[#`<head>`]] de la page.
L'élément **`<title>`** définit le titre du document (qui est affiché dans la barre de titre du navigateur ou dans l'onglet de la page). Cet élément ne peut contenir que du texte, les balises qu'il contiendrait seraient ignorées.

#### `<h1>-<h6>`
Les éléments HTML **`<h1>`** à **`<h6>`** représentent les six niveaux de titre de section. 
`<h1>` correspond au niveau de section le plus haut et `<h6>` correspond au niveau le plus faible.
D'un point de vue [[SEO]], il est important d'insérer les titres dans l'ordre (h4 sous h3, h1 au dessus de h2, etc...)

Code :
```html

<h1>Titre de niveau 1</h1>
<h2>Titre de niveau 2</h2>
<h3>Titre de niveau 3</h3>
<h4>Titre de niveau 4</h4>
<h5>Titre de niveau 5</h5>
<h6>Titre de niveau 6</h6>
```
Résultat :
<h1>Titre de niveau 1</h1>
<h2>Titre de niveau 2</h2>
<h3>Titre de niveau 3</h3>
<h4>Titre de niveau 4</h4>
<h5>Titre de niveau 5</h5>
###### Titre de niveau 6

