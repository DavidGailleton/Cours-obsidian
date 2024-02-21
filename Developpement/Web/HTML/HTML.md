## Définition
Le langage HTML est un langage à balises, comme son nom l’indique : HyperText Markup Language, Langage à Balises Hypertextes.

L’objectif du HTML est de décrire la structure des pages web et d’indiquer le contenu sémantique de chaque élément constitutif de ces pages. Le HTML décrit le contenu des pages web à l’aide d’éléments HTML qui sont constitués de balises. Chaque élément est dédié à l’affichage d’un type de contenu donné. Vous avez des éléments HTML qui affichent les titres, les images, les tableaux, les formulaires…

### La sémantique

Le HTML est donc bien un langage sémantique : chaque élément doit être utilisé dans le cadre de sa définition et les agents utilisateurs attendent un contenu donné pour chaque élément. 
Par exemple, l’élément HTML `<div>` est fait pour contenir un paragraphe de texte et non un tableau, l’élément HTML `<img>` est fait pour contenir une image et non un champ de formulaire. Pour que vos pages web soient valides et bien interprétées par les navigateurs, vous devez respecter cette sémantique.

Voire plus [[Sémantique]]

## Éléments et structures

### Éléments

Un [[Elements]] HTML est compose d'une balise d'ouverture et d'une balise de fermeture: 
``` html
<p> contenu </p>
```

Il faut noter que certains éléments HTML n'ont pas de balise fermante : 
``` html
<hr>
```

Chaque élément HTML peut avoir un ou plusieurs [[Attributs]] : 

``` html
<p id="test" > ceci est un paragraphe </p>

<img src="images/images.jpg" alt="image not found!" title="Titre de l'image">
```

### Structures

Conception d'une page web

Pour concevoir vos pages, vous devez réfléchir en termes de « conteneur ». Un conteneur, comme son nom l’indique, inclut un contenu de type très varié.

Dans ces conteneurs, vous pourrez placer du texte, des images, des formulaires, des liens, des tableaux… Mais vous pourrez aussi avoir des conteneurs plus « petits » comme pour mettre en évidence un ou plusieurs mots, ou pour définir une cellule de tableau.

Les conteneurs servent aussi à structurer vos pages. Vous pourrez ainsi utiliser des conteneurs pour insérer un entête de page, une colonne latérale (une sidebar en anglais), un pied de page, une barre de navigation…









#### Les balises titres : cf code

#### Les listes



##### Insertion de liens pour les pages web

Par essence même, le Web est constitué de liens hypertextes : les pages sont reliées par des liens hypertextes. Et le
HTML contient bien le mot hypertexte dans son abréviation, il correspond au H de HyperText Markup Language.
Vous allez pouvoir lier des pages entre elles, d’un site à l’autre, mais aussi au sein d’une même page de votre site.
Vous insérerez des liens vers des adresses de messagerie, vers des réseaux sociaux et pour télécharger des fichiers
par exemple.
Enfin, notez que les liens sont des éléments de type en ligne (inline).


La structure d'un lien html 

On utilise la balise `<a></a>` pour inserer des liens


Les liens que vous allez insérer auront plusieurs destinations possibles. Ils peuvent cibler une page de votre site ou une page d’un autre site. Dans le premier cas, l’URL pourra être relative, dans le second, l’URL devra être absolue.



#### Utilisation des images en HTML

L’élément `<img>` est fait pour insérer des images d’illustration directement liées au contenu rédactionnel. D’un point
de vue sémantique, cet élément n’est pas fait pour appliquer une image de fond à un entête
ou toute autre zone
d’affichage dans la page. Pour cela, il faut utiliser une règle CSS.

L'attribut src permet de specifier le chemin d'acces vers l'image qu'on souhaite afficher.


#### Les formulaires en HTML 

Les formulaires sont insérés dans l’élément `<form>`. Dans cet élément, nous trouverons tous les champs utiles et les boutons de validation et d’annulation.

Les attributs acceptes par l'element form: 
- action: indique l'URL qui va prendre en charge les donnees saisies par le formulaire
- method: specifie si les donnees seront envoyes via http avec la methode GET ou POST.
- name: le nom du formulaire
- enctype: indique le type MIME des donnees envoyees.

https://developer.mozilla.org/fr/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types



