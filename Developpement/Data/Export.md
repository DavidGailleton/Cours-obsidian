Python peut être utilisé pour lire les données de différents endroits, y compris les bases de données et les fichiers. Deux types de fichiers sont souvent utilisés : .txt et .csv. Vous pouvez importer et exporter les fichiers avec la fonctionnalité intégrée de Python ou le package CSV.

## Chargez des données avec les fonctions intégrées de Python

Pour lire et écrire un fichier, vous pouvez utiliser la fonction intégrée   `open()`  , qui requiert deux paramètres : _le nom du fichier_ et _le mode_. 

**Nom du fichier :** le chemin d’accès au fichier que vous voulez lire ou dans lequel vous voulez écrire.

**Mode :** le mode que vous voulez utiliser pour le fichier. Les options principales sont :

- Lire :   `"r"`
    
- Écrire (écraser) :   `"w"`
    
- Continuer d’écrire :   `"a"`
    
- Lire et écrire (sans écraser) :   `"r+"`
    

Pour créer un nouveau fichier appelé « bonjour.txt » et y écrire « Hello, world! », utilisez le code ci-dessous :
```python
fichier = open("hello.txt", "w")
fichier.write("Hello, world!")
fichier.close()
```
Vous pouvez aussi utiliser l’instruction  `with`  pour fermer automatiquement le fichier à la fin du bloc :
```python
with open("file.txt") as fichier:
    for ligne in fichier:
        # faire quelque chose avec une ligne
        print(ligne)
```
Avec ce code, le fichier d’entrée va être affiché ligne par ligne. Vous avez probablement remarqué que nous n’avons pas spécifié de mode dans   `open()`  ... C’est tout simplement parce que le mode d’ouverture par défaut est la lecture, ou   `"r"`  !

## Le package CSV
La méthode   `open()`  peut lire et écrire sur les fichiers .txt et .csv, mais vous pouvez aussi utiliser le package **CSV** de Python pour lire et écrire dans les fichiers CSV. Ce package offre plus de fonctionnalités.

> **La [documentation officielle de Python sur le format CSV](https://docs.python.org/fr/3/library/csv.html) explique que le package CSV _vous permet de dire « écris ces données dans le format préféré par Excel » ou « lis les données de ce fichier généré par Excel », sans connaître les détails précis du format CSV utilisé par Excel._

Quand vous utilisez le package CSV, vous devez aussi utiliser la fonction   `open()`  pour ouvrir le fichier. Vous pouvez ensuite utiliser les méthodes   `reader()`  ou   `writer()`  sur le fichier pour le lire ou y écrire.

#### Lisez les fichiers externes

Commençons avec la lecture des fichiers externes. Disons que vous avez un fichier CSV nommé_`couleurs_preferees.csv`_qui ressemble à ça : 
```csv
nom,metier,couleur_preferee
Jacob Smith,Ingénieur en informatique,Violet
Nora Scheffer,Stratégiste numérique,Bleu
Emily Adams,Responsable Marketing,Orange
```
La méthode   `.reader()`  va prendre tout le texte dans un CSV, le parser ligne par ligne et convertir chaque ligne dans une liste de chaînes. Vous pouvez utiliser différents délimiteurs pour décider de la manière de séparer chaque colonne, mais le séparateur le plus commun est une virgule. L’extrait de code ci-dessous lit le fichier CSV et affiche chaque ligne.

```python
import csv

with open('couleurs_preferees.csv') as fichier_csv:
    reader = csv.reader(fichier_csv, delimiter=',')
    for ligne in reader:
        print(ligne)
```

Le résultat sera comme ceci :

```python
['nom', 'metier', 'couleur_preferee']
['Jacob Smith', 'Ingénieur en informatique', 'Violet']
['Nora Scheffer', 'Stratégiste numérique', 'Bleu']
['Emily Adams', 'Responsable Marketing', 'Orange']
```

Bien que cette approche puisse être utile parfois, la ligne d’en-tête est considérée comme la même que les autres. Une méthode plus utile pour lire les fichiers CSV, tout en reconnaissant les en-têtes pour identifier les colonnes, est la méthode  `DictReader()`  . Cette méthode sait que la première ligne est un en-tête, et sauvegarde les autres lignes en tant que **dictionnaires**. Chaque clé est un nom de colonne, et la valeur est la valeur de la colonne.

Le code ci-dessous montre comment utiliser la méthode  `DictReader()`  .
```python
import csv

    with open('couleurs_preferees.csv') as fichier_csv:
        reader = csv.DictReader(fichier_csv, delimiter=',')
        for ligne in reader:
            print(ligne['nom'] + " travaille en tant que " + ligne['metier'] + " et sa couleur préférée est " + ligne['couleur_preferee'])
```
Le résultat affichera :
```
Jacob Smith travaille en tant que Ingénieur en informatique et sa couleur préférée est Violet
Nora Scheffer travaille en tant que Stratégiste numérique et sa couleur préférée est Bleu
Emily Adams travaille en tant que Responsable Marketing et sa couleur préférée est Orange
```
## Écrivez dans des fichiers externes

Pour comprendre comment écrire dans des fichiers externes, revenons sur notre exemple d’extraction de données web. Nous avons déjà écrit le code pour extraire et transformer les données du site d’informations et de communication du gouvernement britannique. Nous avons sauvegardé tous les **titres** et **descriptions** dans des listes de chaînes de caractères. Maintenant, nous pouvons utiliser les fonctions   `.writer()`  et   `.writerow()`  pour écrire les données dans le fichier CSV.
```python
# Créer une liste pour les en-têtes
en_tete = ["titre", "description"]

# Créer un nouveau fichier pour écrire dans le fichier appelé « data.csv »
with open('data.csv', 'w') as fichier_csv:
    # Créer un objet writer (écriture) avec ce fichier
    writer = csv.writer(fichier_csv, delimiter=',')
    writer.writerow(en_tete)
    # Parcourir les titres et descriptions - zip permet d'itérer sur deux listes ou plus à la fois
    for titre, description in zip(titres, descriptions):
        # Créer une nouvelle ligne avec le titre et la description à ce moment de la boucle
        ligne = [titre, description]
        writer.writerow(ligne)
```
