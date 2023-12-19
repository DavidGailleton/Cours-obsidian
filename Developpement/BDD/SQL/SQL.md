SQL est un System de [[Base de données]] fonctionnant avec des tables
## SELECT
L'utilisation la plus courante de SQL consiste à lire des données issues de la base de données. Cela s'effectue grâce à la commande SELECT, qui retourne des enregistrements dans un tableau de résultat Cette commande peut sélectionner une ou plusieurs colonnes d'une table.
```sql
SELECT nom_du_champ FROM nom_du_tableau
```

### DISTINCT
supprime les doublons
```SQL
SELECT DISTINCT * FROM drugs
```

### AS (alias)
AS vas changer le nom de la colonne lu par un alias :
```SQL
SELECT antecedant_medicaux AS antecedant FROM patient
```
## FROM
Selectionne la table souhaité

## WHERE

Permet d'ajouter une condition :
```sql
SELECT * FROM patient WHERE ville = 'paris'
```
### IN

### BETWEEN

### LIKE
#### %
Le signe % permet de remplacer tous les caractèrers
#### __
Le signe `_` permet de remplacer seulement 1 caractère

### IS
#### NULL
#### NOT NULL
## GROUP BY


## HAVING

## { UNION | INTERSECT | EXCEPT }

## ORDER BY

## LIMIT

## OFFSET

## ALTER TABLE
ALTER permet de modifié la structure d'une table
