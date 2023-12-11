Le chapitre sur l'ordonnancement se base sur celui des [[Graphes]]

## Tableau de durée

Pour constituer un [[Graphes]] orienté, il nous faut un tableau de durée et d'antériorité :

Taches | Durée | Antériorité
:--: | :--: | :--:
A | 3 | 
B | 4 | A
C | 5 | A
D | 2 | A
E | 2 | B, C
F| 3 | D

Sur ce tableau, l'antériorité est la tache qui doit être **terminé** avant de commencer celle si. 
## Graphes par niveau

À partir du tableau, on réalise un premier graphe appelé graphe de niveau dont les sommets sont les tâches et qui permet de mettre en évidence les antériorités :

![[Pasted image 20231211122049.png]]
## Graphes orienté

On ordonne le graphe des taches par niveaux, en ajoutant une tache  "Debut" et une tache "Fin".
Chaque sommet est représenté par un petit tableau comme ci-dessous:
![[Pasted image 20231211121046.png]]
**Souvent, les marges ne sont pas présentes.**

On remplace en suite les taches du [[#Graphes par niveau]] par le tableau ci dessus :
- Avec la date au plus tot :
On traite les sommets par niveaux en partant du début.
Pour chaque sommet $i$ on note la date $t_i$ qui est la longueur du plus long chemin de la tâche initiale à la tâche $i$
![[Pasted image 20231211122330.png]]
- Puis la date au plu tard :
On traite les sommets en partant de la fin (en marquant **10** pour le sommet « fin »).
Pour chaque sommet on note la date $t_i^*$ qui est la longueur du plus court chemin de la tâche $i$ à la tâche « fin ».
![[Pasted image 20231211122349.png]]


