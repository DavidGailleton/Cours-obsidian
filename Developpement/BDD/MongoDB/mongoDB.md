# MongoDB

MongoDB est une [[Base de données]] noSQL, contrairement a une base SQL, elle n'a aucune contrainte de données.

## Format
En MongoDB, les données sont stockés dans des fichiers JSON.
 Exemple :
```json
{"users": [
    { "username": "testuser", "password": "azerty" },
    { "username": "testuser2", "password": "qwerty" }
  ]
}
```

Les données noSQL sont stocké sous forme de documents et de colections.

Une collection est un groupe de documents MongoDB. C'est l'equvalent d'une table dabs un systeme de gestion de base de données. les collectins n'imposent pas de schema précis. Les documents présents au seins d'une meme collection peuvent avoir des champs différents.
Malgré cela, tous les documents d'une même collection sont généralement similaires ou ont un usage similaire.

Un document est un ensemble de données clé-valeur. Les schema des documents est dit "dynamique".

## Types de données

Nativement le format JSON prend en charge : 
- boolean
- numerique
- chaine de caractères
- tableau
- objet
- null (marque l'absence de valeur)

A ces types, mongoDB vient ajouter : 
- le type Date: stock sous la forme d'un entier signé de 8 octets qui représente le nombre de second écoulé depuis le 1 janvier 1970.
- le type ObjectID: Type interne utilis& par mongoDB pour garantir l'utinicite des identifiants generés par la base de donées.
- Les type entiers NumberLong (8 octets) et NumberInt (4 octets): par défaut, MongoDB considere que les nombres sont des nombres a virgule flottante stocké sur 8 octets
- le type NumberDecimal (16 octets): Permet d'avoir un chiffres flottant stocké sur 16 octets

Ces données sont stocké dans des fichiers [BSON](https://www.mongodb.com/basics/bson)

## Ligne de commandes

Pour utiliser MongoDB en ligne de commande noo utilise `mongod` :
```bash
mongod --port 27017 --dpath /data/db --logpath /tpm/mongodb
```

Se connecter a la BDD on utilise `mongo`:
```bash
mongo --host lien.moncluster.org --port 27017
```

Lister les BDD:
```bash
show databases
ou
show dbs
```

En gneral apres un fresh install de mongodb vous avez 3 bases disponibles : `admin`, `config`, et `local`.
Elles servent a gerer les roles, les autorisations, la gestion de MongoDB, du paraetrage d'instance.

Pour savoir sur quelle base de donéeson se trouve actuellement il suffit de taper la commande `db`, pour lister les collections presentes dans votre bases vous pouvez entrer: `show collections`

Pour switcher de base on utilise la comande `use maDb`

Il est possible en utilisant `use`, de se connecter a une base inexistante, c'est lorsque vous inserez votre premier document dans unecollection de cette base qu'elle sera créée:
```bash
use maBaseDeDonnees
db.maCollection.insert({"une_clé": "une_valeur"})
```

`find` montrera les valeurs trouvé :
```bash
db.maCollection.find()
return:
  {
    "_id": ObjectID("...")
    "une_cle": "une_valeur"
  }
```

L'insertion de document se fait comme ceci : `db.collection.insert(<document ou tableau>)`

