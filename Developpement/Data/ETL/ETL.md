**ETL** signifie **extraction**, **transformation** et **chargement** (Extract, Transform, Load, en anglais). En d'autres termes, c'est une manière sophistiquée de dire que vous collectez des données d'un endroit, que vous les arrangez et que vous les stockez ailleurs. L'extraction de données web est un exemple d'ETL, où vous **récupérez** des données d'un site web, les **formatez** comme vous le souhaitez, et les **stockez** dans un fichier CSV ou une base de données.

En premier temp il faut connaitre le fonctionnement de [[HTML]] et [[Python]]

## Le package Requests

Pour extraire des données à partir d’un site web, nous devons utiliser le package **Requests**. Rappelez-vous qu’il fournit la fonctionnalité de faire des requêtes HTTP. Nous pouvons l’utiliser puisque nous essayons d’obtenir des données à partir d’un site web qui utilise le protocole HTTP (par exemple, [**http:**//google.com](https://google.com/)). 

Le package Requests contient une fonction **.get()** qui peut être utilisée pour récupérer le code HTML du site.  

Pour appliquer ça à l’exercice d’extraction de données web, nous allons utiliser le package **Requests** pour obtenir le code HTML de la page d’informations et de communication britannique. Dans le code ci-dessous, nous importons le package, nous sauvegardons l’URL que nous voulons extraire dans une variable  `url`  , et nous utilisons la méthode  `.get()`  pour récupérer les données HTML. Si vous exécutez le code ci-dessous, vous verrez le code source HTML affiché dans la console. 

```python
import requests

url = "https://www.gov.uk/search/news-and-communications"
page = requests.get(url)

# Voir le code html source
print(page.content)
```

Même si nous avons récupéré tout le code HTML dans notre code, c’est toujours incompréhensible. Il nous faut encore savoir comment **parser** les éléments exacts que nous voulons. Et nous pouvons utiliser Beautiful Soup pour faire ça !

>**Parser** signifie « parcourir le contenu d'un texte ou d'un fichier en l'analysant pour vérifier sa syntaxe ou en extraire des éléments. »

## Le package Beautiful Soup

Maintenant que nous avons le code source HTML, nous devons le parser. On parse le HTML avec les attributs HTML   `class`  et   `id`  mentionnés plus tôt.

Nous pouvons utiliser Beautiful Soup pour trouver les éléments qui peuvent être identifiés avec la classe et l’id que nous voulons trouver. Comme pour n’importe quel package, nous allons utiliser pip pour installer Beautiful Soup.
```
pip install beautifulsoup4
```

Ensuite, nous allons importer Beautiful Soup et créer un objet « soup » à partir du HTML que nous avons eu avec les requêtes :
```python
import requests

from bs4 import BeautifulSoup

url = "https://www.gov.uk/search/news-and-communications"
page = requests.get(url)
soup = BeautifulSoup(page.content, 'html.parser')
```
La variable   `soup`  que nous avons créée avec Beautiful Soup possède toutes les fonctions qui facilitent l’obtention de données à partir de HTML. Avant de récupérer les données de la page d’informations et de communication britannique, nous allons parcourir certaines fonctionnalités de Beautiful Soup avec l’extrait HTML ci-dessous.
```html
<html>
    <head><title>Les chiens les plus mignons</title></head>
    <body>
    <p class="title"><b>Les meilleures races de chiens</b></p>
    <p class="chiens">
      <a href="http://exemple.com/labradoodle" class="race" id="lien1">LabraDoodle</a>,
      <a href="http://exemple.com/retriever" class="race" id="lien2">Golden Retriever</a> et
      <a href="http://exemple.com/carlin" class="race" id="lien3">Carlin</a>
    </p>
    </body>
</html>
```

Une fois qu’on a créé un objet « soup » à partir du HTML, nous pouvons accéder à tous les éléments de la page très facilement !
```python
# Récupération du titre de la page HTML
>>> soup.title
<title><Les chiens les plus mignons></title>
# Récupération de la chaîne de caractères du titre HTML
>>> soup.title.string
"Les chiens les plus mignons"

# Trouver tous les éléments avec la balise <a>
>>> soup.find_all('a')
[ <a href="http://exemple.com/labradoodle" class="race" id="lien1">LabraDoodle</a>,
<a href="http://exemple.com/retriever" class="race" id="lien2">Golden Retriever</a>
<a href="http://exemple.com/carlin" class="race" id="lien3">Carlin</a>]

# Trouver les éléments avec l’id du « lien1 »
>>> soup.find(id="lien1")
<a href="http://exemple.com/labradoodle" class="race" id="lien1">LabraDoodle</a>

#Trouver tous les éléments p avec la classe « title »
>>> soup.find_all("p", class_="title")
"Les meilleures races de chiens"
```
