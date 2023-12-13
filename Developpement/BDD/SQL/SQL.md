## SELECT
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
#### %a
#### a%

#### %a%

#### pa%on
## GROUP BY


## HAVING

## { UNION | INTERSECT | EXCEPT }

## ORDER BY

## LIMIT

## OFFSET
