Un `TRIGGER` est une procédure stockée au sein d'une base de données qui est appelée lorsqu'un évènement précis a lieu au niveau de la base de données.

Par exemple, un `TRIGGER` peut être déclenché lors d'une insertion dans une table spécifique.

On note que :
- Les `TRIGGERS` ne peuvent pas être exécutés manuellement
- Les `TRIGGERS` ne dépendent pas de paramètres externes
- On ne peut pas commit ou rollback un **transaction** au sein d'un `TRIGGER`

## Syntaxe

```sql
CREATE trigger <nom du trigger>
<BEFORE | AFTER>
INSERT / UPDATE / DELETE
ON <nom de la table>
FOR EACH ROW
<corp du trigger>
```

