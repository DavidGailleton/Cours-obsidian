# Connexion de l'API a une BDD MongoDB avec Mongoose

## Initialisation du projet

L'ORM utilisé pour la connexions est `Mongoose` :
```bash
npm install mongoose
```

Pour connecter l'API a la BDD, on utilise le middleware `.connect` :
```js
mongoose.connect(
    'mongodb+srv://<userName>:<Password>@cluster0.ov3vohk.mongodb.net/<bdd>?retryWrites=true&w=majority'
)
```

Pour eviter que l'API se lance sans que la BDD soit connecter, on utilise des promesse :
```js
mongoose.connect(
    'mongodb+srv://<userName>:<Password>@cluster0.ov3vohk.mongodb.net/<bdd>?retryWrites=true&w=majority'
).then(result => {
    app.listen(3003, () => {
        console.log("App is listening on port 3003");
    });
}).catch(e => console.log('Connexion a la BDD echoue' + e) );
```

## Créer des Schema et Models

Avant tout, il faut créer des schema et des models dans `models/exemple.js` :

```js
const mongoose = require('API/REST/API JS/mongoose');
const Schema = mongoose.Schema;

const productSchema = new Schema(
    {
        name: {
            type: String,
            require: true
        },
        price: {
            type: Number,
            require: true
        }
    }
);

module.exports = mongoose.model("Product", productSchema);
```

## Insérer des données

Pour insérer des données au sein de la base de données on utilise le middle war `.save` :
```js
await products.save();
```
Pour les insérer depuis un méthode post:
```js
const name = req.body.name;
const price = req.body.price;

const product = new Product({
    name: name,
    price: price
});

await product.save()
```
Pour finir, il est possible d'exporter le tout au sein d'une fonction afin qu'elle soit utiliser via un routes :
```js
exports.createProduct = (req, res) => {
    const name = req.body.name;
    const price = req.body.price;
    
    const product = new Product({
        name: name,
        price: price
    });

    product.save()
        // Promesses permettant de repondre à la requette en l'affichant
        .then(result => {
            res.status(201).json({
                message: 'Products created successfully',
                post: result
            })
        })
        // Si la les données ne sont pas inséré au seins de la BDD,
        // la console renverra une erreur
        .catch(error => {
            console.log('error: ', error)
        })
};
```

## Afficher les données d'une BDD

Afin d'afficer les données contenue dans la base, on utilise le middle ware `.find`:
```js
  const product = await Product.find();
```

Pour l'exporter au sein d'une fonction utilisable dans une route et configurer le renvoie d'une requette HTTP :
```js
exports.getProducts = async (req, res) => {
    const product = await Product.find();

    res.status(200).json({
        message: 'Products find',
        post: product
    });
};
```

## Mettre a jour des données

