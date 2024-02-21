### Connexion à la base de données

Pour commencer, vous devez établir une connexion à votre base de données MySQL en utilisant PDO.

```php
<?php
$host = '127.0.0.1';
$db   = 'nom_de_la_base_de_donnees';
$user = 'utilisateur';
$pass = 'mot_de_passe';
$charset = 'utf8mb4';

$dsn = "mysql:host=$host;dbname=$db;charset=$charset";
$options = [
    PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    PDO::ATTR_EMULATE_PREPARES   => false,
];

try {
    $pdo = new PDO($dsn, $user, $pass, $options);
} catch (\PDOException $e) {
    throw new \PDOException($e->getMessage(), (int)$e->getCode());
}
```

Ce code crée une nouvelle instance de PDO pour se connecter à une base de données MySQL. Les options configurées garantissent que PDO lancera une exception en cas d'erreur, utilisera par défaut le mode de récupération associatif pour les résultats, et n'émulera pas les requêtes préparées.

### Exécution des requêtes

#### Requêtes simples

```php
$sql = "INSERT INTO utilisateurs (nom, email) VALUES ('John Doe', 'john.doe@example.com')";
$pdo->exec($sql);
```

Cette commande exécute une requête SQL simple qui n'a pas besoin de préparation car elle ne contient pas de données externes.

#### Requêtes préparées

Les requêtes préparées offrent une meilleure sécurité, en particulier pour prévenir les injections SQL.

```php
$sql = "INSERT INTO utilisateurs (nom, email) VALUES (:nom, :email)";
$stmt = $pdo->prepare($sql);
$stmt->execute(['nom' => 'Jane Doe', 'email' => 'jane.doe@example.com']);
```

Dans cet exemple, une requête préparée est utilisée pour insérer des données dans une table. Les placeholders `:nom` et `:email` sont remplacés par les valeurs réelles en utilisant la méthode `execute`, ce qui évite les injections SQL.

### Récupération de données

```php
$sql = "SELECT nom, email FROM utilisateurs WHERE id = :id";
$stmt = $pdo->prepare($sql);
$stmt->execute(['id' => 1]);
$user = $stmt->fetch();
echo $user['nom'] . ", " . $user['email'];
```

Cet exemple montre comment récupérer une ligne spécifique depuis la base de données en utilisant une requête préparée. La méthode `fetch` récupère la première ligne correspondant aux critères de recherche.

### Gestion des erreurs

Avec les options de configuration spécifiées lors de la connexion, PDO lancera une exception en cas d'erreur, que vous pouvez capturer et gérer :

```php
try {
    // Tentative d'exécution d'une requête
} catch (\PDOException $e) {
    echo "Erreur de base de données : " . $e->getMessage();
}
```

Envelopper vos opérations de base de données dans des blocs `try-catch` vous permet de gérer élégamment les erreurs, par exemple en affichant un message d'erreur sans révéler d'informations sensibles.

### Conclusion

L'utilisation de PDO pour interagir avec MySQL en PHP est recommandée pour plusieurs raisons, notamment la sécurité améliorée grâce aux requêtes préparées, la flexibilité offerte par l'abstraction de la base de données (permettant de changer facilement de type de base de données si nécessaire), et les fonctionnalités avancées de gestion des erreurs. Ces exemples de base montrent comment établir une connexion, exécuter des requêtes simples et préparées, récupérer des données et gérer les erreurs avec PDO.
