## Les représentations

Les graphes peuvent être représentés par des diagrammes

![[Capture d’écran du 2023-08-28 16-24-48.png]]

Mais également par des tableau

![[Capture d’écran du 2023-08-28 14-08-17 1.png]]
 
Nous pouvons aussi les représenter par des [[Calcul matriciel]]
![[Capture d’écran du 2023-08-28 14-10-49.png]]

## Les chemins et Circuits

### Chemin

Un Chemin est un ensemble de longueur.

Chemin de longueur 2 : 

![[Capture d’écran du 2023-08-28 15-02-21.png]]

Chemin de longueur 3 :

![[Capture d’écran du 2023-08-28 15-02-57.png]]

### Circuit

Un circuit est un ensemble de chemins formant une boucle :

![[Capture d’écran du 2023-08-28 16-26-03.png]]
## Calcule des chemins

Il est possible de trouver le nombre de chemin disponible grâce aux [[Calcul matriciel]]
Pour cet exemple nous allons utilise ce graphe :
![[Capture d’écran du 2023-08-28 15-02-57.png]]

Pour trouver l'ensemble des chemins de longueur 1 nous allons créer une matrice

 M | X1 | X2 | X3 | X4
 :---: | :---: | :---: | :---: | :---: 
X1 | 0 | 1 | 0 | 0 
X2 | 0 | 0 | 1 | 0
X3 | 0 | 0 | 0 | 1
X4 | 0 | 0 | 0 | 0

Pour trouver l'ensemble des chemins de longueur 2, il suffit de mettre la matrice au carré :

 M² | X1 | X2 | X3 | X4
 :---: | :---: | :---: | :---: | :---: 
X1 | 0 | 0 | 1 | 0 
X2 | 0 | 0 | 0 | 1
X3 | 0 | 0 | 0 | 0
X4 | 0 | 0 | 0 | 0

Pour les chemins de longueur 3, au cube :

 M³ | X1 | X2 | X3 | X4
 :---: | :---: | :---: | :---: | :---: 
X1 | 0 | 0 | 0 | 1 
X2 | 0 | 0 | 0 | 0
X3 | 0 | 0 | 0 | 0
X4 | 0 | 0 | 0 | 0

Et ainsi de suite...
