## IF / ELSE
### If
Avec une instruction **if**, vous pouvez exécuter certaines lignes de code uniquement si une certaine condition est **vraie (True)**. Si cette condition est **fausse (False),** le code ne s’exécutera pas. 

Par exemple, pour notre exemple sur le temps qu’il fait :
```python
if ensoleille:
    print("on va à la plage !")
```

### Else
Il est possible d'exécuter un bloc de code si la condition `if` n'est pas respecter avec `else` :
```python
ensoleille = True
if ensoleille:
    print("on va à la plage !")
else:
    print("on reste à la maison !")
```

### Elif
Les **instructions if/elif/else** vous permettent de définir des conditions multiples. Le mot-clé **`elif`**  vous permet d’ajouter autant de conditions que vous voulez. Vous devez ensuite terminer avec une instruction **else**.
```python
ensoleille = False
neige = True
if ensoleille:
    print("on va à la plage !")
elif neige:
    print("on fait un bonhomme de neige")
else:
    print("on reste à la maison !")
```

## Operateurs logique
Il est également possible d'utiliser des [[Operateurs#Operateur logique|operateurs logique]] :
```python
avec_soleil = True
en_semaine = False
if avec_soleil and not en_semaine:
    print("on va à la plage !")
elif avec_soleil and en_semaine:
    print("on va au travail !")
else:
    print("on reste à la maison !")
```
**Attention** : Il est important de garder en tête l'ordre d'évaluation des conditions dans une expression conditionnelle, surtout lorsque des opérateurs "or" et "and" sont utilisés. L'opérateur "or" s'arrêtera dès qu'il trouvera une condition vraie, tandis que l'opérateur "and" s'arrêtera dès qu'il rencontrera une condition fausse. Il est donc conseillé de bien réfléchir à l'**ordre des conditions afin d'optimiser la performance du programme**, et d’éviter des évaluations inutiles.

## Conditions complexes
Les expressions comparatives vous permettent de comparer différentes expressions entre elles, et d’évaluer si une expression est vraie ou fausse.

Si vous avez deux valeurs,**`a`** et **`b`** , vous pouvez utiliser les opérateurs de comparaison suivants dans Python : 

- Égal à : a   `==`  b
    
- Non égal à : a   `!=`  b
    
- Moins que : a   `<`  b
    
- Moins que ou égal à : a   `<=`  b
    
- Plus que : a   `>`  b
    
- Plus que ou égal à : a   `>=`  b


```python
nombre_de_sieges = 30
nombre_dinvites = 25

if nombre_dinvites < nombre_de_sieges:
    # autoriser plus d’invités
else:
    # ne pas autoriser plus d’invités
```

## les match cases
Le match est une fonctionnalité pour faciliter la comparaison de valeurs à l'aide de motifs. Le but est de **simplifier** la syntaxe de certaines structures courantes qui utilisent des blocs if, elif et else. Le match offre une alternative plus **concise** et plus **lisible**.

Découvrons les mots-clés utilisés dans cette nouvelle structure conditionnelle. Le mot-clé `match`  est utilisé pour indiquer le **début** d'un bloc de match case, suivi de la variable à évaluer. Le mot-clé `case`  est utilisé pour **vérifier** si une valeur donnée correspond à une condition spécifique dans ce bloc. Le symbole  `_`   est utilisé pour définir une action à effectuer si aucune condition ne correspond.

Par exemple, si vous voulez tester la valeur d'une variable et exécuter une action différente pour chaque cas, vous pouvez utiliser le match. Imaginons que vous vouliez exécuter une action différente selon la valeur de la variable fruit :
```python
fruit = "pomme"
match fruit:
    case "pomme":
        print("J'aime les pommes !")
    case "banane":
        print("Je n'aime pas les bananes.")
    case "orange":
        print("Les oranges sont bonnes pour la santé.")
    case _:
        print("Je ne connais pas ce fruit.")
```

