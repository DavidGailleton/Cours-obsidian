Les [[Variables]] en [[Python]] se déclare de cette manière :
```python
>>> livre = "Harry Potter"
>>> print(livre)
Harry Potter
```
Le [[Type]] de la variable est ici choisi automatiquement.

Il est possible de modifier la valeur d'une variable :
```python
>>> print(livre)
Harry Potter
>>> livre = "Hunger Games"
>>> print(livre)
Hunger Games
```

## f-string
Une **f-string** est une chaîne de caractères précédée d'un  `f`   (ou  `F`   ), et contenant des expressions entre accolades `{}`  qui seront évaluées lors de l'exécution du programme :
```python
nom = "Dupont"
prenom = "Jean"
age = 30

print(f"Bonjour, je m'appelle {prenom} {nom} et j'ai {age} ans.")
```

## Nommer un variable
Un nom de variable doit refléter son contenu, comme le nom sur un carton. Voici quelques recommandations générales pour choisir un nom :

- **Utilisez des noms descriptifs dans votre code.**  
    Vous avez déjà retrouvé un vieux classeur dans un carton avec le nom « Trucs importants » sur la couverture ? C’était frustrant, n’est-ce pas ? Les noms de variables descriptifs et spécifiques simplifient la vie, et facilitent la lecture et la modification de votre code. Au lieu de   `quantite`  (ou pire,  `qte`  ), ajoutez des détails :  `quantite_en_stock`  ,  `solde_actuel`  , etc.
    
- **Utilisez des mots complets.**  
    Évitez d’abréger ou de raccourcir les mots autant que possible, même si une alternative plus courte paraît évidente. Par exemple,  `revenu_annuel`  est plus clair que  `rev_annuel`  .
    
- **Suivez une convention d’appellation commune.** Il est recommandé de suivre la convention d'appellation du [[snake_case]] en Python, conformément à la **PEP8** qui est le standard de la syntaxe en Python : des noms composés de plusieurs mots séparés par des tirets bas (  `_`  ) comme  `nombre_de_chats`  ,   `reponse_finale`  ,   `le_meilleur_developpeur_python_du_monde`  , etc.
    
- **Commencez avec une lettre ou le tiret bas.**  
    Un nom de variable ne peut pas commencer par un nombre.
    
- **Utilisez uniquement les lettres, les chiffres et  le tiret du bas... et surtout pas d'accents !**  
    Par exemple, écrivez  `bonjour_1`  mais pas  `bonjour_#1`  .
    
- **N’oubliez pas que les noms de variables sont sensibles à la casse.**  
    `age,`   `Age`  et   `AGE`sont trois variables différentes.