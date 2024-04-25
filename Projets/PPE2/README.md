# CovoituReact

Ce document vas présenter mon projet `CovoituReact`.
Le but de l'application est de répondre aux normes **QHSE** et **RSE** de l'entreprises.
Il permet de réduire l'impact écologique des trajets fait au quotidien en voiture, et met également en avant le prix d'un trajet pour motiver les collaborateur à faire du covoiturage. 
## Presentation

CovoituReact est une App web permettant de mettre en relation plusieurs personne au sein d'une entreprise afin qu'ils fassent du covoiturage.

Ce projet utilise une structure dite MERN Stack, c'est a dire qu'il utilise MongoDB, Express.js, React.js et Node.js pour réaliser une application Full-Stack.
Ces différentes solutions vont se structurer de cette manière :
![[MERN-stack.webp]]
## Outils utilisés

### Front-end
Pour la partie Front-end il sera utiliser 3 frameworks :
- REACT JS : REACT n'est pas réellement un framwork mais plutot une bibliothèque de composent JS open source. Le bute de REACT est de créer des interfaces, mais également de minimiser les bugs d'interface en utilisant des composants.
- Tailwind CSS : Tailwind CSS est un framework CSS possedant des `class` préfaites. Il permet de créer du `style` au sein de son site sans jamais quitter son code HTML. Contrairement a la plupart des frameworks CSS comme Bootstrap, c'est un framework completement personnalisable.
- TypeScript : TypeScript est un language de programmation open-source, ou pour etre plus précis, un surensemble de Javascript, c'est a dire que le code JavaScript est fonctionnel et TypeScript. TypeScript est beaucoup moins permissif que JS (donc beaucoup moins sensible a la casse), et il permet de faire de la programmation typé et orienté objet.

### Back-end
La partie back-end vas utiliser 2 frameworks :
- Express : Express est actuellement le framework le plus populaire sur Node, il permet entre autre :
  - Écrire des fonctions de traitement pour différentes requêtes HTTP répondant à différentes URI
  - Intégrer avec les moteurs de rendu de « vues » dans le but de générer des réponses en insérant des données dans des templates
  - Ajouter des requêtes de traitement « middleware » où vous le voulez dans le tunnel gestionnaire de la requête
- Mongoose : Mongoose est un mappeur de document objet (Object-Relational Mapping). 

utiliser [swagger-ui-express](https://www.npmjs.com/package/swagger-ui-express)

## Visuel du site

Le site arbore une interface minimaliste.

### Arrivée sur le site
#### Connexion
![[Pasted image 20231002154552.png]]
#### Inscription
![[Pasted image 20231002154638.png]]

### Les pages du site

A l'arrivée sur le site, tout est accessible clairement.
#### Page d'accueil
![[Pasted image 20231002155054.png]]
A noter que le nom d'utilisateur est un menu déroulant :
![[Pasted image 20231002155235.png]]
#### Poster une annonce
![[Pasted image 20231002155331.png]]
#### Trouver un covoiturage
![[Pasted image 20231002155406.png]]
#### Mes informations
![[Pasted image 20231002155442.png]]
#### Mon annonce 
![[Pasted image 20231002155522.png]]


## Fonctionnement

Voici un schéma technique du fonctionnement du site :
![[CovoituReact fonctionnement.png]]
### React rooter dom
Les URLs du site sont configurer de cette manière grace à `react-router-dom` :
```tsx
// Crée une instance de BrowserRouter avec la structure des routes  
const router = createBrowserRouter([  
  {  
    path: "/",  
    element: <Root />,  
    errorElement: <Error />,  
    children: [  
      {  
        path: "/",  
        element: <Default />,  
      },  
      {  
        path: "search",  
        element: <ProductPage />,  
      },  
      {  
        path: "post",  
        element: <Post />,  
      },  
      {  
        path: "myProduct",  
        element: <MyProduct />,  
      },  
      {  
        path: "userInformation",  
        element: <UserInfo />,  
      },  
    ],  
  },  
  {  
    path: "/login",  
    element: <Login />,  
    errorElement: <Error />,  
  },  
  {  
    path: "/signup",  
    element: <Signup />,  
    errorElement: <Error />,  
  },  
]);
```
### Connexion au site
#### Vérification de validité de la connexion
A l'arrivé sur la racine du site (`/`), l'API va vérifier si le jeton JWT contenue dans le *local storage* existe et est **valide** :
```js
// Importation du module jsonwebtoken pour gérer les jetons JWT (JSON Web Tokens)  
const jwt = require('jsonwebtoken');  
  
// Exportation du middleware qui vérifie l'authentification de l'utilisateur  
module.exports = async (req, res, next) => {  
  try {  
    // Récupération du jeton d'authentification depuis l'en-tête de la requête  
    const token = await req.headers.authorization.split(' ')[1];  
  
    // Vérification et décryptage du jeton en utilisant la clé secrète JWT (process.env.JWT_KEY)  
    const decodedToken = await jwt.verify(token, process.env.JWT_KEY);  
  
    // Stockage des données de l'utilisateur extraites du jeton dans req.user  
    const user = await decodedToken;  
    req.user = user;  
  
    // Passage au middleware suivant  
    next();  
  } catch (err) {  
    // En cas d'erreur lors de la vérification du jeton  
    res.status(401).json({  
      err: new Error('Invalid request !'),  
    });  
  }  
};
```
L'API est appelé grâce au fetch suivant :
```tsx
// Envoi de la requête au point de terminaison d'authentification  
fetch(`http://localhost:3003/auth/auth-endpoint`, requestOptions)  
  .then((response) => {  
    // Vérification de la réponse HTTP  
    if (!response.ok) {  
      throw new Error("Request failed"); // En cas d'échec de la requête, génère une erreur  
    }  
    return response.json(); // Convertit la réponse en format JSON  
  })  
  .then((data) => {  
    console.log(data); // Affiche les données de la réponse dans la console  
  })  
  .catch((error) => {  
    console.error(error); // En cas d'erreur, affiche l'erreur dans la console  
    if (error instanceof Error && error.message === "Request failed") {  
      // Si l'erreur est due à une requête échouée, redirige vers la page de connexion  
      window.location.replace("/login");  
    }  
  });
```
Si l'API renvoie une bonne réponse alors rien ne se passera, sinon le site sera redirigé sur */login*.

#### Connexion
Sur la page de connexion sera demandé le mail et le mot de passe. A la soumission du formulaire, cette fonction sera appelé :
```tsx
const handleSubmit = (event: React.FormEvent<HTMLFormElement>) => {  
  event.preventDefault(); // Empêche la soumission du formulaire par défaut  
  
  // Récupération des éléments du formulaire  const emailInput = event.target.email;  
  const passwordInput = event.target.password;  
  
  // Récupération des valeurs saisies par l'utilisateur  
  const email: string = emailInput.value;  
  const password: string = passwordInput.value;  
  
  // Création d'un objet avec les données du formulaire  
  const formResult = {  
    email: email.toLowerCase(),  
    password: password,  
  };  
  
  // Envoi des données au serveur via une requête fetch  
  fetch("http://localhost:3003/auth/login", {  
    method: "PUT",  
    headers: {  
      "Content-type": "application/json",  
    },  
    body: JSON.stringify(formResult),  
    redirect: "follow",  
  })  
    .then((response) => response.json())  
    .then((response) => {  
      localStorage.setItem("JWT", response.token);  
      localStorage.setItem("name", response.name);  
      localStorage.setItem("email", response.email);  
      window.location.replace("/");  
    });  
};
```
Cette méthode fetch appel cette fonction de l'API :
```js
// Fonction de connexion de l'utilisateur  
exports.login = (req, res, next) => {  
  const email = req.body.email; // Récupération de l'email depuis le corps de la requête  
  const password = req.body.password; // Récupération du mot de passe depuis le corps de la requête  
  let loadedUser;  
  User.findOne({ email: email }) // Recherche de l'utilisateur par email dans la base de données  
    .then((user) => {  
      if (!user) {  
        const error = new Error('A user with this email could not be found.');  
        error.statusCode = 401;  
        throw error; // Erreur si l'utilisateur n'est pas trouvé  
      }  
      loadedUser = user;  
      return bcrypt.compare(password, user.password); // Comparaison du mot de passe fourni avec le mot de passe haché enregistré  
    })  
    .then((isEqual) => {  
      if (!isEqual) {  
        const error = new Error('Wrong password!');  
        error.statusCode = 401;  
        throw error; // Erreur si le mot de passe est incorrect  
      }  
      const token = jwt.sign(  
        {  
          email: loadedUser.email,  
          userId: loadedUser._id.toString(),  
        },  
        process.env.JWT_KEY, // Création d'un token JWT avec les informations de l'utilisateur  
        { expiresIn: '1h' }, // Durée de validité du token (1 heure)  
      );  
      res.status(200).json({  
        token: token,  
        userId: loadedUser._id.toString(),  
        name: loadedUser.name.toString(),  
        email: loadedUser.email.toString(),  
      }); // Réponse avec le token et les informations de l'utilisateur  
    })  
    .catch((err) => {  
      if (!err.statusCode) {  
        err.statusCode = 500;  
      }  
      next(err);  
    });  
};
```

Une fois la réponse valide de l'API reçu, la page sera redirigé vers la racine du site.
#### Inscription
Dans le cas ou l'utilisateur n'a pas de compte, il est toujours possible de s'inscrire.
Le formulaire comprend un nom d'utilisateur, un mail et un mot de passe. Une fois soumis, la fonction suivante est appelé :
```tsx
const postUser = (event: React.FormEvent<HTMLFormElement>) => {  
  event.preventDefault(); // Empêche la soumission du formulaire par défaut  
  
  // Récupération des éléments du formulaire  const usernameInput = event.target.username;  
  const emailInput = event.target.email;  
  const passwordInput = event.target.password;  
  
  // Récupération des valeurs saisies par l'utilisateur  
  const username: string = usernameInput.value;  
  const email: string = emailInput.value;  
  const password: string = passwordInput.value;  
  
  // Création d'un objet avec les données du formulaire  
  const formResult = {  
    name: username,  
    email: email,  
    password: password,  
  };  
  
  // Envoi des données au serveur via une requête fetch  
  fetch("http://localhost:3003/auth/signup", {  
    method: "PUT",  
    headers: {  
      "Content-type": "application/json",  
    },  
    body: JSON.stringify(formResult),  
  }).then((res) => {  
    console.log(res);  
  });  
};
```
Le fetch appel la fonction suivante de l'API :
```js
// Fonction pour l'inscription d'un utilisateur  
exports.signup = (req, res, next) => {  
  const errors = validationResult(req); // Validation des erreurs dans la requête  
  if (!errors.isEmpty()) {  
    const error = new Error('Validation failed.');  
    error.statusCode = 422;  
    error.data = errors.array(); // Stockage des erreurs de validation  
    throw error;  
  }  
  const email = req.body.email; // Récupération de l'email depuis le corps de la requête  
  const name = req.body.name; // Récupération du nom depuis le corps de la requête  
  const password = req.body.password; // Récupération du mot de passe depuis le corps de la requête  
  
  bcrypt  
    .hash(password, 12) // Hachage du mot de passe avec un coût de 12  
    .then((hashedPw) => {  
      const user = new User({  
        email: email,  
        password: hashedPw, // Stockage du mot de passe haché dans la base de données  
        name: name,  
      });  
      return user.save(); // Enregistrement de l'utilisateur dans la base de données  
    })  
    .then((result) => {  
      res.status(201).json({ message: 'User created!', userId: result._id }); // Réponse en cas de succès  
    })  
    .catch((err) => {  
      if (!err.statusCode) {  
        err.statusCode = 500;  
      }  
      next(err);  
    });  
};
```
Si la réponse est bonne, alors la page est rediriger vers */login*.
### Navigation sur le site
#### Page d'accueil
La page `/` n'appel que la fonction permettant d'extraire le nom d'utilisateur du *local storage* : 
```tsx
localStorage.getItem("name")
```
#### Chercher une annonce
La page `/search` importe les annonce depuis la BDD :
```tsx
// Fonction pour récupérer les produits depuis le serveur  
const fetchProducts = async () => {  
  const response = await fetch("http://localhost:3003/products/getproducts/");  
  const responseValue = await response.json();  
  setProducts(responseValue.posts); // Met à jour l'état avec les produits récupérés  
  setLoading(false); // Met fin au chargement une fois les données récupérées  
};
```
Le fetch appel cette fonction :
```js
exports.getProducts = (req, res, next) => {  
  Product.find() // Recherche tous les produits dans la base de données  
    .then((posts) => {  
      res.status(200).json({ message: 'Fetched product successfully.', posts: posts }); // Répond avec les produits trouvés  
    })  
    .catch((err) => {  
      if (!err.statusCode) {  
        err.statusCode = 500;  
      }  
      next(err);  
    });  
};
```
Une fois importer, le site map les objets importer :
```tsx
products.length > 0 &&  
products.map((product: Product, index) => (  
  <div  
    key={index}  
    className="bg-white rounded shadow-md p-4 relative"  
  >  
    {/* Affiche les détails du produit */}  
    <ProductCard product={product} />  
    <div className="mt-4">  
      <h3 className="text-xl font-semibold">{product.name}</h3>  
      {/* Appelle sendEmail au clic */}  
      <a  
        href={`mailto:${product.mail}`}  
        onClick={sendEmail}  
        className="text-blue-500 hover:underline mt-2 block"  
      >  
        Envoyer un e-mail  
      </a>  
    </div>  </div>))
```
La fonction `sendEmail` permet d'appeler un `mailto` :
```tsx
const sendEmail = () => {  
  // Utilisez `window.location.href` pour ouvrir le client de messagerie par défaut  
  window.location.href = `mailto:${product.mail}`;  
};
```
#### Poster une annonce
En arrivant sur la page `/post`, un fonction permettant de vérifier si l'utilisateur à déjà poster une annonce :
```tsx
// Fonction pour vérifier si un utilisateur a déjà créé une annonce avec son nom  
const checkIfPostExistWithName = async () => {  
  const UserName = localStorage.getItem("name"); // Récupère le nom de l'utilisateur depuis le stockage local  
  console.log(UserName);  
  const response = await fetch(  
    `http://localhost:3003/products/getproducts/name/${UserName}`  
  ).then((response) => response.json());  
  // Si la réponse contient "Product found", alors on redirige vers la page d'accueil  
  if (response.message === "Product found") {  
    window.location.href = "/myproduct"; // Redirection vers la page "myproduct"  
  }  
  console.log(response);  
};  
  
checkIfPostExistWithName(); // Appelle la fonction de vérification lors du chargement de la page
```
Le fetch appel cette fonction :
```js
exports.getByName = async (req, res, next) => {  
  const productName = req.params.name; // Récupère le nom du produit depuis les paramètres de la requête  
  Product.find({ name: productName }) // Recherche le produit par nom  
    .then((product) => {  
      if (product.length === 0) {  
        // Aucun produit correspondant n'a été trouvé  
        res.status(404).json({  
          message: 'Product not found',  
        });  
      } else {  
        // Un produit correspondant a été trouvé  
        res.status(200).json({  
          message: 'Product found',  
          post: product,  
        });  
      }  
    })  
    .catch((error) => {  
      if (!error.statusCode) {  
        error.statusCode = 500;  
      }  
      next(error);  
    });  
};
```
Si une annonce est trouvé avec le nom de l'utilisateur, alors le si redirigera la page vers `/myproduct`, sinon le formulaire s'affichera :
A la soumission du formulaire, si toutes les cases sont bien remplie, alors il importera les différents éléments au seins de la bdd :
```tsx
const createPost = (event: React.FormEvent<HTMLFormElement>) => {  
  event.preventDefault(); // Empêche la soumission par défaut du formulaire  
  // Récupère les valeurs des champs du formulaire  const departInput = event.target.depart;  
  const l100Input = event.target.l100;  
  const carInput = event.target.car;  
  const heureInput = event.target.heure;  
  const distanceInput = event.target.distance;  
  const placeInput = event.target.place;  
  const name = localStorage.getItem("name"); // Récupère le nom de l'utilisateur depuis le stockage local  
  const email = localStorage.getItem("email"); // Récupère l'e-mail de l'utilisateur depuis le stockage local  
  
  // Récupère les valeurs des champs sous forme de chaînes de caractères ou de nombres  const depart: string = departInput.value;  
  const l100: number = l100Input.value;  
  const heure: number = heureInput.value;  
  const distance: number = distanceInput.value;  
  const place: number = placeInput.value;  
  const car: string = carInput.value;  
  
  // Crée un objet avec les données du formulaire  
  const formResult = {  
    name: name,  
    mail: email,  
    depart: depart,  
    car: car,  
    heure: heure,  
    l100: l100,  
    distance: distance,  
    place: place,  
  };  
  
  // Envoie les données du formulaire au serveur  
  fetch("http://localhost:3003/products/createproduct", {  
    method: "POST",  
    headers: {  
      "Content-type": "application/json",  
    },  
    body: JSON.stringify(formResult),  
  })  
    .then((res) => {  
      console.log(res);  
    })  
    .then(() => {  
      window.location.replace("/myproduct"); // Redirige vers la page de l'utilisateur après la création du post  
    });  
};
```
Le fetch :
```tsx
exports.createProduct = async (req, res) => {  
  const name = req.body.name; // Récupère les données du corps de la requête  
  const mail = req.body.mail;  
  const depart = req.body.depart;  
  const car = req.body.car;  
  const heure = req.body.heure;  
  const l100 = req.body.l100;  
  const distance = req.body.distance;  
  const place = req.body.place;  
  
  const product = new Product({  
    name: name,  
    mail: mail,  
    depart: depart,  
    car: car,  
    heure: heure,  
    l100: l100,  
    distance: distance,  
    place: place,  
  });  
  
  product  
    .save() // Enregistre le produit dans la base de données  
    .then((result) => {  
      res.status(201).json({  
        message: 'Products created successfully',  
        post: result,  
      });  
    })  
    .catch((error) => {  
      console.log('error: ', error);  
      // Envoyer une réponse appropriée en cas d'erreur  
    });  
};
```
Si la réponse de l'API est bonne, alors l'utilisateur sera rediriger vers `/myproduct`
#### Mes produits
La page `/myproduct` utilise le même appel fetch que la page `/search`([[#Chercher une annonce|Cliquez ici]]) mais en filtrant la post par nom après l'importation de tout les objets. Il utilise également 3 useState :
```tsx
const [loading, setLoading] = useState(true);  
const [products, setProducts] = useState<Product[]>([]);  
const [hasPosts, setHasPosts] = useState(false); // Ajoutez un état pour suivre si l'utilisateur a des posts
```
```tsx
const fetchProducts = async () => {  
  const response = await fetch("http://localhost:3003/products/getproducts");  
  const responseValue = await response.json();  
  const nameFromLocalStorage = localStorage.getItem("name");  
  let myPost;  
  
  if (Array.isArray(responseValue.posts) && nameFromLocalStorage) {  
    const filteredArray = responseValue.posts.filter(  
      (item: { name: string }) => item.name === nameFromLocalStorage  
    );  
  
    console.log(filteredArray);  
    myPost = filteredArray;  
    setHasPosts(myPost.length > 0); // Mettez à jour l'état hasPosts en fonction des posts  
  } else {  
    console.log(  
      "La valeur 'name' n'a pas été trouvée dans le local storage ou la réponse ne contient pas de tableau 'posts'."  
    );  
  }  
  
  console.log(responseValue.posts); // Ceci affiche le tableau complet de produits  
  console.log(responseValue);  
  setProducts(myPost); // Utilisez directement myPost, pas myPost.posts  
  setLoading(false);  
};
```

Cette page permet également de supprimer une annonce en appelant la fonction `handleDeleteProject` :
```tsx
const handleDeleteProduct = async (productName: string) => {  
  try {  
    const response = await fetch(`http://localhost:3003/deleteproduct/`, {  
      method: "DELETE",  
      headers: {  
        "Content-type": "application/json",  
        Authorization: "Bearer " + localStorage.getItem("JWT"),  
      },  
      body: JSON.stringify({ name: productName }),  
    });  
  
    if (response.ok) {  
      // Suppression réussie, mettez à jour la liste des produits après suppression  
      const updatedProducts = products.filter(  
        (product) => product.name !== productName  
      );  
      setProducts(updatedProducts);  
      window.location.href = "/post";  
    } else {  
      // Gérer les erreurs de suppression, afficher un message d'erreur, etc.  
      console.error("Erreur lors de la suppression de l'annonce");  
    }
```
Le fetch correspondant :
```js
exports.deleteProductByName = async (req, res) => {  
  try {  
    console.log("Nom de l'utilisateur à supprimer :", req.params.name);  
    const product = await Product.findOneAndDelete({ name: ObjectName(req.params) });  
    console.log('Produit supprimé :', product);  
    if (product) {  
      // Suppression réussie  
      res.status(200).json({  
        message: 'Product deleted successfully',  
        post: product,  
      });  
    } else {  
      // Aucun produit correspondant trouvé  
      res.status(404).json({  
        message: 'Product not found',  
      });  
    }  
  } catch (error) {  
    console.error("Erreur lors de la suppression de l'annonce", error);  
    res.status(500).json({  
      message: 'Internal server error',  
    });  
  }  
};
```
#### Mes informations
Pour finir, la page `/userInformation` permet simplement de visualiser son nom d'utilisateur et son mail via un import du local storage :
```tsx
// Déclaration des états locaux pour stocker le nom et l'e-mail  
const [name, setName] = useState("");  
const [email, setEmail] = useState("");  
  
useEffect(() => {  
  // Effet de côté exécuté lors du chargement du composant  
  // Récupérez le nom et l'e-mail depuis le localStorage s'ils existent  const storedName = localStorage.getItem("name");  
  const storedEmail = localStorage.getItem("email");  
  
  if (storedName && storedEmail) {  
    // Si le nom et l'e-mail sont présents dans le localStorage, mettez à jour les états locaux  
    setName(storedName);  
    setEmail(storedEmail);  
  }  
}, []); // Le tableau vide [] signifie que cet effet ne s'exécute qu'une fois lors du montage initial du composant
```

## Sources
https://www.freecodecamp.org/news/how-to-build-a-fullstack-authentication-system-with-react-express-mongodb-heroku-and-netlify/
