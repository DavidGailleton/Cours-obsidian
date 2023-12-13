# SQL

## Introduction à MySQL
### Qu'est-ce que MySQL?

MySQL est un système de gestion de [[Base de données]] relationnelle (SGBDR) open source. Il a été créé par MySQL AB, qui a été acquise par Oracle Corporation en 2010. MySQL est une base de données très populaire et est utilisée dans de nombreux sites Web et applications. Il prend en charge de nombreux langages de programmation, notamment PHP, Python, Java, C++, et est compatible avec plusieurs systèmes d'exploitation, notamment Windows, Linux et Mac OS.

### Pourquoi utiliser MySQL?

MySQL est une base de données rapide, fiable et évolutive. Elle est également gratuite et open source, ce qui la rend accessible à tous les développeurs. MySQL est compatible avec de nombreux langages de programmation et est capable de gérer de grandes quantités de données. Il est également sécurisé et offre des fonctionnalités avancées telles que les transactions ACID (Atomicité, Cohérence, Isolation, Durabilité) et la réplication.

### Installation de MySQL

L'installation de MySQL peut varier selon le système d'exploitation que vous utilisez. Vous pouvez télécharger l'installateur MySQL à partir du site Web de MySQL (https://www.mysql.com/downloads/). Suivez les instructions d'installation pour installer MySQL sur votre système d'exploitation. Après l'installation, vous pouvez accéder à MySQL en utilisant la ligne de commande ou un outil de gestion de base de données, tel que MySQL Workbench.

## Les bases de données relationnelles
### Concepts de base des bases de données relationnelles

Une base de données relationnelle est une collection de tables qui contiennent des données liées les unes aux autres. Les données sont organisées en lignes et colonnes, et chaque colonne représente un attribut ou une caractéristique des données. Les tables sont reliées entre elles par des clés primaires et des clés étrangères, ce qui permet d'établir des relations entre les données et d'effectuer des requêtes complexes.

### Les tables

Une table est une collection de données organisées en lignes et colonnes. Chaque table a un nom unique et chaque colonne a un nom qui représente l'attribut ou la caractéristique des données qu'elle contient. Les lignes contiennent les données elles-mêmes. Chaque ligne est identifiée de manière unique par une clé primaire, qui peut être une colonne spécifique ou une combinaison de colonnes. Les tables peuvent être créées, modifiées et supprimées en utilisant des requêtes SQL (Structured Query Language).

### Les relations entre tables

Les tables dans une base de données relationnelle peuvent être liées les unes aux autres à l'aide de clés primaires et de clés étrangères. Une clé primaire est une colonne ou une combinaison de colonnes qui identifie de manière unique chaque ligne d'une table. Une clé étrangère est une colonne qui fait référence à la clé primaire d'une autre table. Les relations entre tables peuvent être de différents types, tels que une relation un-à-un, une relation un-à-plusieurs et une relation plusieurs-à-plusieurs. Les requêtes SQL peuvent être utilisées pour récupérer des données à partir de plusieurs tables en utilisant des jointures, qui combinent les données de différentes tables en fonction de leurs relations.

## Le langage SQL
### Les commandes SQL de base

**SQL** (Structured Query Language) est un langage de programmation utilisé pour gérer et interagir avec des bases de données relationnelles. Les commandes SQL de base incluent :

- SELECT : pour sélectionner des données à partir d'une ou plusieurs tables
- INSERT : pour insérer de nouvelles données dans une table
- UPDATE : pour modifier des données existantes dans une table
- DELETE : pour supprimer des données d'une table
- CREATE : pour créer une nouvelle table ou une nouvelle base de données
- ALTER : pour modifier la structure d'une table existante
- DROP : pour supprimer une table ou une base de données

### Sélection de données

La commande SELECT est utilisée pour sélectionner des données à partir d'une ou plusieurs tables. La syntaxe de base est la suivante :

``` SQL 
SELECT column1, column2, ... FROM table_name;
```

Cette commande sélectionne les colonnes spécifiées (column1, column2, etc.) à partir de la table spécifiée (table_name). Vous pouvez également utiliser la clause WHERE pour filtrer les résultats en fonction d'une condition spécifique, telle que :

``` SQL 
SELECT column1, column2, ... FROM table_name WHERE condition;
```



### Tri de données

La commande ORDER BY est utilisée pour trier les résultats d'une requête SQL. La syntaxe de base est la suivante :

``` SQL 
SELECT column1, column2, ... FROM table_name ORDER BY column_name ASC/DESC;
``` 

Cette commande sélectionne les colonnes spécifiées (column1, column2, etc.) à partir de la table spécifiée (table_name) et les trie par ordre croissant (ASC) ou décroissant (DESC) en fonction de la colonne spécifiée (column_name). Vous pouvez également trier les résultats en fonction de plusieurs colonnes en spécifiant plusieurs colonnes dans la clause ORDER BY.

### Filtrage de données

La clause WHERE est utilisée pour filtrer les données sélectionnées à partir d'une ou plusieurs tables. La syntaxe de base est la suivante :

``` SQL
SELECT column1, column2, ... FROM table_name WHERE condition;
```

La condition peut être une comparaison entre deux valeurs, une comparaison entre une valeur et NULL, une comparaison entre une valeur et une plage de valeurs, une vérification d'appartenance à une liste, etc.

### Mise à jour de données

La commande UPDATE est utilisée pour modifier des données existantes dans une table. La syntaxe de base est la suivante :

``` SQL 
UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;
```

Cette commande modifie les valeurs de colonnes spécifiées (column1, column2, etc.) dans la table spécifiée (table_name) en fonction de la condition spécifiée (WHERE condition). Vous pouvez modifier les valeurs de plusieurs colonnes en une seule commande.

### Suppression de données

La commande DELETE est utilisée pour supprimer des données d'une table. La syntaxe de base est la suivante :

``` SQL
DELETE FROM table_name WHERE condition;
```

Cette commande supprime les lignes de la table spécifiée (table_name) qui correspondent à la condition spécifiée (WHERE condition). Si la condition n'est pas spécifiée, toutes les lignes de la table seront supprimées.








Partie TP:

Création de la base de données :

CREATE DATABASE mydatabase;
USE mydatabase;



Création d'une table pour stocker les informations sur les clients :

CREATE TABLE users (
  id INT NOT NULL AUTO_INCREMENT,
  first_name VARCHAR(50) NOT NULL,
  last_name VARCHAR(50) NOT NULL,
  age INT,
  PRIMARY KEY (id)
);

CREATE TABLE orders (
  id INT NOT NULL AUTO_INCREMENT,
  user_id INT NOT NULL,
  item_name VARCHAR(50) NOT NULL,
  price DECIMAL(10,2) NOT NULL,
  order_date DATE NOT NULL,
  PRIMARY KEY (id),
  FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE TABLE clients (
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  nom VARCHAR(50) NOT NULL,
  prenom VARCHAR(50) NOT NULL,
  email VARCHAR(100) NOT NULL,
  telephone VARCHAR(20) NOT NULL,
  adresse VARCHAR(200) NOT NULL,
  ville VARCHAR(50) NOT NULL,
  pays VARCHAR(50) NOT NULL
);



Insertion de données de test dans la table clients :

INSERT INTO clients (nom, prenom, email, telephone, adresse, ville, pays)
VALUES
('Dupont', 'Jean', 'jean.dupont@example.com', '01 23 45 67 89', '12 Rue de la Paix', 'Paris', 'France'),
('Martin', 'Sophie', 'sophie.martin@example.com', '01 45 67 89 01', '24 Rue du Commerce', 'Lyon', 'France'),
('Lefebvre', 'Pierre', 'pierre.lefebvre@example.com', '01 56 78 90 12', '36 Rue Saint-Louis', 'Marseille', 'France'),
('Garcia', 'Maria', 'maria.garcia@example.com', '01 23 45 67 89', '2 Calle Mayor', 'Barcelone', 'Espagne'),
('Rossi', 'Luigi', 'luigi.rossi@example.com', '01 23 45 67 89', '10 Via Roma',


INSERT INTO users (first_name, last_name, age)
VALUES
  ('John', 'Doe', 25),
  ('Jane', 'Doe', 30),
  ('Bob', 'Smith', 40),
  ('Alice', 'Jones', 35);

INSERT INTO orders (user_id, item_name, price, order_date)
VALUES
  (1, 'Shirt', 20.00, '2022-03-15'),
  (1, 'Shoes', 50.00, '2022-03-18'),
  (2, 'Dress', 70.00, '2022-03-19'),
  (3, 'Pants', 30.00, '2022-03-20'),
  (4, 'Jacket', 100.00, '2022-03-22');



  Sélectionnez tous les utilisateurs de la table "users".
```SQL
  SELECT * FROM `users` WHERE 1
```

Sélectionnez tous les articles de la table "orders" qui ont été commandés avant le 20 mars 2022.
```SQL
SELECT item_name FROM `orders` WHERE order_date<'2022-03-20';
```

Sélectionnez les noms et les âges de tous les utilisateurs dont l'âge est supérieur ou égal à 30 ans.
```SQL
SELECT last_name, age FROM users WHERE age>=30;
```

Sélectionnez le nombre total d'articles commandés pour chaque utilisateur.
```SQL
SELECT COUNT(*) FROM `orders` GROUP BY user_id;
```

Mettez à jour le nom de famille de l'utilisateur ayant l'ID 3 pour qu'il devienne "Johnson".
```SQL
UPDATE users SET last_name = 'Jhonson' WHERE id=3;
```

Supprimez tous les utilisateurs dont l'âge est inférieur à 25 ans.
```sql
DELETE FROM users WHERE age<25;
```
