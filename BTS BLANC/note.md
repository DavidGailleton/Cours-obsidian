## Blocage de l'utilisateur

nouvelle table : **tentative_connexion**(id_med, success(booleen), date(date_time))

modification de la table Médecin : Ajoute de la valeur booléen désactiver

### Ajout d'une connexion dans la table tentative_connexion

```sql
INSERT INTO tentative_connexion(id_med, success, date)
VALUES (@id_med, @success, DateTime.now())
```

### Après 5 tentatives de connexion

```sql
SELECT MAX(date)
FROM tentative_connexion
WHERE success = true
```
La date est contenue dans la variable `date`

```sql
SELECT *
FROM tentative_connexion
WHERE date > @date
```
En comptant de nombre de lignes retournés on connait le nombre de tentative infructueuse. 

## Modif ordonnance
```sql
UPDATE ordonnance
SET posologie_ord = @posologie, date_creation_ord = @date_creation, duree_ord = @duree, instruction_ord = @instruction, id_medic = @id)
WHERE posologie_ord = @posologie, date_creation_ord = @date_creation, duree_ord = @duree, instruction_ord = @instruction, id_med = @id, id_pat = @id, id_medic = @id;
```

## Supprimer ordonnance
```sql
DELETE FROM ordonnance 
WHERE posologie_ord = @posologie, date_creation_ord = @date_creation, duree_ord = @duree, instruction_ord = @instruction, id_med = @id, id_pat = @id, id_medic = @id;
```