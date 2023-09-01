## `<div>`

Pour des raison de [[SEO]], il est déconseillé
#### L'element header

L’élément `<header>` permet d’insérer une zone d’affichage pour les entêtes.
Ces entêtes peuvent être utilisés à plusieurs endroits :
- au niveau de la page, c’est l'entête de page classique, souvent placé en haut de l’écran, avec un logo, un slogan, une barre de navigation principale...
- En haut d'un article

#### L'element footer:
L’élément `<footer>` permet d’insérer une zone d’affichage pour les pieds de page. Nous retrouvons la même
sémantique que pour les entêtes.
Ces pieds de page peuvent être définis pour la page ou pour une autre zone d’affichage de celle ci, comme un article. Notez que l’usage d’un `<footer>` n’implique pas forcément l’usage d’un `<header>`.

#### L'element nav: 
L’élément `<nav>`, comme son nom le laisse supposer, est dédié à l’affichage d’une barre de navigation avec des liens hypertextes. Mais attention, ne vous sentez pas obligé de n’avoir qu’une seule zone de navigation par page. Vous pouvez créer autant d’éléments `<nav>` que vous avez de navigations différentes dans vos pages, à partir du moment où chacun d’entre eux est bien identifié. L’élément `<nav>` est plutôt dédié à la navigation principale du site,
à la création de liens entre les pages du site. 
Vous pouvez inclure une navigation principale `<nav>` dans un entête `<header>` et une navigation secondaire `<nav>` dans un pied de page `<footer>`, par exemple.

#### L'element main: 

L’élément `<main>` permet d’indiquer le contenu principal de la page. Ce contenu doit être unique et ne pas être répété dans la page. De plus, le W3C indique précisément son  contexte d’utilisation : il ne doit pas être utilisé à l’intérieur, comme élément inclus, dans les éléments `<article>`, `<aside>`, `<footer>`, `<header>` ou `<nav>`.

#### L'element section: 

L’élément <section> permet de regrouper des éléments partageant une même thématique. Cela permet de
regrouper dans un même élément un contenu structuré, avec son entête
et son pied de page. L’utilisation de
plusieurs éléments </section> distinguera plusieurs parties, plusieurs sections au sein d’une même page, avec
d’autres éléments de structure imbriqués.