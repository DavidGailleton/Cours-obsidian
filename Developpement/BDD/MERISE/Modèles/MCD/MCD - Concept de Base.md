## Entité
- Permet de modéliser un **ensemble d'objet de même nature**
- Un élément appartenant à cette entité est appelé **occurrence**
![[Pasted image 20231201124257.png]]
## Propriété ou Attribut
- Données **élémentaire** d'une entité
- Dans une occurrence la propriété accepte **une seule valeur**
![[Pasted image 20231201124355.png]]

## L'identifiant ou la clef
- Un **Attribut** ou propriété de l'identité
- Permet de trouver (identifier une occurence d'entité **unique**
![[Pasted image 20231201124510.png]]
### Exemple
![[Pasted image 20231201124530.png]]
### Clef composée
L'identifiant peut être composé de plusieurs attributs (clef composée).
Pour ce faire on peut utiliser plusieurs attribut pour trouver un appartement spécifique comme par exemple, dans un appartement utiliser le numéro d'appartement et le numéro d'immeuble :
![[Pasted image 20231201125107.png]]

### ID
- Pour éviter tous doublon on peut utiliser un identifient unique que l'on nomera généralement **id_nomEntite** et celui-ci est généralement **séquentiel** (**Il est important de ne pas oublier de soulignée les clé primaire**)
- Un entier auto-incrément
- Une combinaison de code avec une partie qui s'incrémente
![[Pasted image 20231201125423.png]]
## Résumé 
![[Pasted image 20231201125456.png]]

## Les cardinalités
Les cardinalités précisent la participation d'une entité à une relation

La cardinalité est représenté par des **parenthèse** contenant 2 chiffres séparé par une virgule. le premier chiffre est le nombre minimal pour lequel une entitée peut ajouter des composant à une **association**. Le second est le nombre maximal (ou **N** pour infini)  
[[MCD - Modèle Conceptuel de Données|MCD]] :

![[Pasted image 20231201132110.png]]
