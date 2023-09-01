
# Le CSS



On peut appliquer du style a certains elements a l'aide l'attribut class. En CSS on cible les elements dont la classe est test de la maniere suivante:
``` CSS
.test {
    test-transform: uppercase;
}
```

On peut aussi en CSS appliquer du style de maniere specifique grace a l'attribut html id:
``` CSS
#test {
    /* ceci est un commentaire  */
}
```


## Structure et regles du CSS

Ceci est une regle de style:
```
selecteur {
    props: valeur
}
```

Les selecteurs :
- ne doivent pas commencer par un chiffre
- ne peuvent pas contenir d'espace, de caracteres speciaux, de caracteres avec accents
-  peuvent contenir des `-` et  des `_`
- sont sensibles a la casse (majuscule/minuscule)


Les expressions regulieres
Lien : https://developer.mozilla.org/fr/docs/Glossary/Regular_expression



## Les selecteurs de pseudo-classes:

Les pseudoclasses permettent de cibler des éléments qui ne sont pas accessibles avec les sélecteurs classiques
et qui prennent un état particulier, comme les liens visités. En ce qui concerne la syntaxe, une pseudoclasse commence toujours par le caractère deux points : et est immédiatement suivie par le nom de la pseudoclasse.


Pour cet apres-midi :

- Preparer la maquette de votre futur site web

- Se documenter sur les outils css Bootstrap / Flexbox et CSSGRid
- Utiliser un (ou plusieurs) de ces outils afin de creer la structure generale de votre (vos) pages web
- Veillez a bien separer les fichiers HTML, CSS et les assets dans des dossiers separes.