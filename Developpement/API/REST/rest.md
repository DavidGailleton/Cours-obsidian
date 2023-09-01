# API REST

L'architecture RESTful est un modele d'architecture de developpement de service Web.

**REST** : (Representational State Transfer) Définit un standart et des contraintes  tels que :
- l'utilisation d'URI pour identifier les ressources
- L'utilisation de methodes HTTP (GET, POST, PUT, DELETE, ...) pour effectuer des opérations sur ces ressources
- La represention des ressources au format JSON ou XML

Les APIs (Application Programming Interface) sont des `interfaces` qui permettent a des application de communiquer entre elles. On s'en sert notamment afin d'echanger des donnnées.

Voici un exemple de JSON qui represente un étudiant ISITECH :
```json
{
  "lastname": "DJEBLI",
  "firstname": "Ayoub",
  "age": 19,
  "addresse": {
    "rue": "rue de la paix",
    "ville": "Paris",
    "Pays": "France"
  },
  "phoneNumbers": [
    {
      "type": "mobile",
      "num": "0836656565"
    },
    {
      "type": "fixe",
      "num": "3630"
    }
  ]
}
```

L'arborescence des fichier ressemble ceci :
```json
├── controller
│   ├── feed.js
├── routes
│   ├── feed.js
├── node_modules
├── package.json
├── package-lock.json
├── index.js
└── .gitignore

```

**Endpoint** : point d'entrée unique vers une ressource, il est constitue d'un verbe qui designe une methode http et d'une url (uri).

Les codes http :
- 2XX: tout s'est bien passé (200: OK, 201: Created)
- 3XX: Redirection
- 4XX: erreur due au client (404: Not found, )
- 5XX: Erreur due au serveur

Pour chaque ressource vous devez mettre en place un CRUD:

- Create:
- Read:
- Update:
- Delete: (soft delete)

Les grands principes REST.