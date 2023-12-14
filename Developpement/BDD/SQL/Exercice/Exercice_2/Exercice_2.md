1.  Obtenir la liste des 10 villes les plus peuplées en 2012
```SQL
SELECT * from villes_france_free ORDER BY ville_population_2012 DESC LIMIT 10

```
2. Obtenir la liste des 50 villes ayant la plus faible superficie
```sql
SELECT * FROM villes_france_free ORDER BY ville_surface ASC LIMIT 50
```
3. Obtenir la liste des départements d'outres-mer, c'est-à-dire ceux dont le numéro de département commencent par "97"
```sql
SELECT * FROM villes_france_free WHERE ville_departement LIKE "97%"
```
4. Obtenir le nom des 10 villes les plus peuplées en 2012, ainsi que le nom du département associé
```sql
SELECT ville_nom, ville_departement FROM villes_france_free ORDER BY ville_population_2012 DESC LIMIT 10
```
5. Obtenir la liste du nom de chaque département, associé à son code et du nombre de commune au sein de ces département, en triant afin d'obtenir en priorité les départements qui possèdent le plus de communes
```sql
SELECT departement_nom, departement_code, COUNT(ville_departement) AS nb_ville FROM villes_france_free INNER JOIN departement ON departement_code = ville_departement GROUP BY departement_code ORDER BY nb_ville DESC
```
6. Obtenir la liste des 10 plus grands départements, en terme de superficie
```sql
SELECT departement_nom, COUNT(ville_surface) AS departement_superficie FROM villes_france_free INNER JOIN departement ON departement_code = ville_departement GROUP BY departement_nom ORDER BY departement_superficie DESC LIMIT 10  
```
7. Compter le nombre de villes dont le nom commence par "Saint"
```sql
SELECT COUNT(ville_nom) FROM villes_france_free WHERE ville_nom LIKE 'SAINT%'
```
8. Obtenir la liste des villes qui ont un nom existants plusieurs fois, et trier afin d'obtenir en premier celles dont le nom est le plus souvent utilisé par plusieurs communes
```sql
SELECT ville_nom, COUNT(ville_nom) AS nb_utilise FROM villes_france_free GROUP BY ville_nom ORDER BY nb_utilise DESC
```
9. Obtenir en une seule requête SQL la liste des villes dont la superficie est supérieur à la superficie moyenne
```sql
SELECT ville_nom, ville_surface FROM villes_france_free GROUP BY ville_nom HAVING ville_surface > (SUM(ville_surface) / COUNT(ville_surface))
```
10. Obtenir la liste des départements qui possèdent plus de 2 millions d'habitants
```sql
SELECT departement_nom, SUM(ville_population_2012) AS population FROM departement INNER JOIN villes_france_free ON ville_departement = departement_code GROUP BY departement_nom ORDER BY population DESC
```
11. Remplacez les tirets par un espace vide, pour toutes les villes commençant par "SAINT-" (dans la colonne qui contient les noms en majuscule)
```sql
UPDATE villes_france_free SET ville_nom = REPLACE(ville_nom, '-', ' ') WHERE ville_nom LIKE 'SAINT-%'
```