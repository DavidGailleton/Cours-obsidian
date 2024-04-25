Représentation :
$\begin{bmatrix}6&-3&-1\\3&-9&2\\-1&1&3\end{bmatrix}$
## Calcules
### Multiplication

Quand on travaille dans l'ensemble des matrices, pour éviter toute confusion on utilise le terme **scalaire** pour désigner un nombre réel.​

Pour **multiplier une matrice par un scalaire**, on multiplie chacun des éléments de la matrice par le scalaire $$2 * \begin{bmatrix}5&2\\3&1\end{bmatrix} = \begin{bmatrix}2*5 & 2*2 \\ 2*3&2*1\end{bmatrix} = \begin{bmatrix}10&4\\6&2\end{bmatrix}$$

Pour multiplier 2 matrices, on additionne le résultat de la multiplication des diagonale.

![[Capture d’écran du 2023-08-28 14-49-36.png]]

### Addition

Pour additionner des matrices, on additionne les éléments situés aux mêmes emplacements dans chacune des matrices. $$A+B = \begin{bmatrix}4&8\\3&7\end{bmatrix} + \begin{bmatrix}1&0\\5&2\end{bmatrix} = \begin{bmatrix}4+1&8+0\\3+5&7+2\end{bmatrix} = \begin{bmatrix}5&8\\8&9\end{bmatrix}$$
### Soustraction

De même, pour soustraire deux matrices, on soustrait les éléments situés aux mêmes emplacements dans chacune des matrices$$C-D = \begin{bmatrix}2&8\\0&9\end{bmatrix} - \begin{bmatrix}5&6\\11&3\end{bmatrix} = \begin{bmatrix}2-5&8-6\\0-11&9-3\end{bmatrix} = \begin{bmatrix}-3&2\\-11&6\end{bmatrix}$$
## Inverse

Pour trouver l'inverse d'une matrice, on utilisera une puissance de $-1$ :

$$A = \begin{bmatrix}2&4\\1&5\end{bmatrix}$$
$$A^{-1} = \begin{bmatrix}\frac{5}{6}&-\frac{2}{3}\\-\frac{1}{6}&\frac{1}{3}\end{bmatrix}$$

## Différents types de matrices

### Matrice identité

La matrice identité se trouve en multipliant un matrice par son inverse :

$$\begin{bmatrix} 5&6\\2&3 \end{bmatrix} * \begin{bmatrix} 5&6\\2&3 \end{bmatrix}^{-1} = \begin{bmatrix} 1&0\\0&1 \end{bmatrix}$$

### Matrice carré
Si le nombre de lignes est égal au nombre de colonnes, alors on dit que la matrice est carré :
$$\begin{bmatrix}2&8&4\\0&9&9\\3&7&2\end{bmatrix}$$

### Matrice booleen

La matrice booléen montre simplement si un chemin est disponible dans un graphe en fonction d'une longueur de chemin précise

### Matrice transitive

Une matrice Transitive montre le nombre de chemin disponible d'un point a l'autre qu'importe sa longueur

## Résolution d'une équation

On prend en les 2 équations :
$2x +5y = 19$ 
$-x + 2y = 4$

On met les coefficient dans une matrice :
$$A = \begin{bmatrix}2&5\\-1&2\end{bmatrix}$$
Les valeurs à trouver dans une autre :
$$X = \begin{bmatrix}x\\y\end{bmatrix}$$
Les résultats dans une autre
$$B = \begin{bmatrix}19\\4\end{bmatrix}$$

Pour résoudre cette équation, on utilise la méthode suivante :
$$AX = B$$
$$A^{-1}AX = A^{-1}B$$
$$I_dX = A^{-1}B$$
$$X = A^{-1}B$$
donc :
$$A^{-1} = \begin{bmatrix}\frac{2}{9}&-\frac{5}{9}\\\frac{1}{9}&\frac{2}{9}\end{bmatrix}$$
$$X = \begin{bmatrix}\frac{2}{9}&-\frac{5}{9}\\\frac{1}{9}&\frac{2}{9}\end{bmatrix} * \begin{bmatrix}19\\4\end{bmatrix} = \begin{bmatrix}2\\3\end{bmatrix}$$
donc $x = 2$ et $y = 3$

