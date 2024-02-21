## Module

Un module en Python est simplement **un fichier** contenant du code Python. Ce code peut contenir des [[Fonction]], des classes, des [[Variable]], etc. Les modules permettent **d'organiser** votre code de manière logique, et de le réutiliser facilement.

Pour utiliser un module, vous pouvez l'importer dans votre code à l'aide du mot-clé `import`  . Par exemple, si vous avez un fichier nommé `mon_module.py`  qui contient une fonction nommée `ma_fonction`  , vous pouvez l'importer ainsi :

```python
import mon_module
resultat = mon_module.ma_fonction()
```

Une fois le module importé dans votre nouveau fichier grâce à la commande `import`  , vous pouvez désormais utiliser la fonction `ma_fonction()`  . Cependant, n'oubliez pas de spécifier le nom du module avant d'appeler la fonction.

Vous pouvez également importer des éléments **spécifiques** d'un module, en utilisant la syntaxe  `from mon_module import ma_fonction`   . Cela vous permet d'utiliser directement la fonction `ma_fonction`  sans avoir à spécifier le nom du module.

```python
from mon_module import ma_fonction
resultat = ma_fonction()
```

> Il est généralement recommandé de placer toutes les déclarations d'importation en **début** de fichier Python, avant toute autre instruction.

## Packages
Un package en Python est simplement un **dossier** contenant un **ensemble de modules** Python. Les packages permettent **d'organiser** votre code en sous-dossiers, et de créer des hiérarchies de modules.

Pour créer un package, vous devez simplement créer un dossier contenant un fichier nommé `__init__.py`  . Ce fichier est utilisé pour initialiser le package, et peut contenir du code d'initialisation si nécessaire.

Pour utiliser un module d'un package, vous devez spécifier le **nom** du package dans l'import. Par exemple, si vous avez un package nommé `mon_package`  qui contient un module nommé `mon_module`  , vous pouvez l'importer ainsi :

```python
import mon_package.mon_module
resultat = mon_package.mon_module.ma_fonction()
```

Tout comme pour les modules, vous pouvez importer les éléments spécifiques du module d'un package en utilisant la syntaxe  `from mon_package.mon_module import ma_fonction`   .

## PIP
>Existe-t-il des packages prêts à être téléchargés pour aider les développeurs à résoudre des problèmes courants plus facilement ?

Bien évidemment ! C'est la magie de Python, qui offre une multitude de packages déjà créés et prêts à être utilisés pour résoudre des problèmes spécifiques. De nombreux packages populaires sont disponibles sur des dépôts en ligne tels que [**PyPI**](https://pypi.org), et peuvent être **facilement** installés à l'aide d'un gestionnaire de packages tel que `pip`  .

Voici quelques exemples de packages populaires, et leurs fonctions :

- [**Requests**](https://fr.python-requests.org/en/latest/) : un package HTTP élégant et simple pour Python. Fréquemment utilisé pour les appels d’interface REST ; 
    
- **[Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)** (ressource en anglais) : un package pour récupérer des données de fichiers HTML et XML ; 
    
- **[Pandas](https://pandas.pydata.org/)** (ressource en anglais) : un outil open source rapide, puissant et accessible pour l’analyse et la manipulation de données. 
    

Des milliers de packages Python sont disponibles pour votre code !
### Installez les packages avec pip

pip est un gestionnaire de packages Python.

>Un gestionnaire de packages ?

Un **gestionnaire de packages** est un outil qui permet d’installer et de gérer des packages supplémentaires dans votre terminal. pip est déjà installé dans Python, comme ça vous êtes prêt à vous y mettre !

Pour installer un package avec pip dans votre terminal, utilisez la méthode suivante :

`pip install <nom-du-package>`

Pour voir les packages déjà installés, vous pouvez écrire le code qui suit :

`pip freeze`

Il va afficher une liste de tous les packages existants, qu’on appelle dépendances, dans votre terminal.