1. Trouver toutes les villes dont le nom commence par la lettre P :
```sql
SELECT * FROM villes_france_free WHERE ville_nom LIKE "P%"
```
2. Selectionner les villes situées dans les departements 75, 77, 78, 91, 92, 93, 94, 95
```sql
SELECT * FROM villes_france_free WHERE ville_departement IN (75, 77, 78, 91, 92, 93, 94, 95)
```
3. Lister distinctement les noms réels de toutes les villes ayant une population en 2010 supérieure à 20 000 habitants
```sql
SELECT ville_nom_reel FROM villes_france_free WHERE ville_population_2010 > 20000
```
4. Trouver les villes dont le code postal est compris entre 75000 et 75020
```sql
SELECT * FROM villes_france_free WHERE ville_code_postal BETWEEN 75000 AND 75020
```
5. Sélectionner les villes qui ne sont pas dans les départements 13, 33, 69
```sql
SELECT * FROM villes_france_free WHERE ville_departement NOT IN (13, 33, 69)
```
6. Lister les villes ayant une population en 2010 entre 10 000 et 50 000 habitants et situées dans le département 75
```sql
SELECT * FROM villes_france_free WHERE ville_population_2010 BETWEEN 10000 AND 50000
```
7. Trouver les villes dont le nom commence par 'A ou 'B'
```sql
SELECT * FROM villes_france_free WHERE ville_nom LIKE 'A%' OR 'B%'
```
8. Sélectionner les villes dont la densité en 2010 est supérieure à 1000 habitants/km2 et ayant une population en 2010 inférieure à 20 000 habitants
```sql
SELECT * FROM villes_france_free WHERE ville_densite_2010 > 1000 AND ville_population_2010 < 20000
```
9. Lister toutes les villes dont le nom réel est différent du nom simple
```sql
SELECT * FROM villes_france_free WHERE ville_nom_reel != ville_nom_simple
```
10. Trouver les villes dont le nom sonore (Soundex) est identique à celui de 'Lyon'
```sql
SELECT * FROM villes_france_free WHERE ville_nom_soundex = 'L500'
```