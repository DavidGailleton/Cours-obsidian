## Exercice 1
### 1.
La manette est petite et à brancher
### 2.

| g\nb | 00  | 01  | 11  | 10  |
| ---- | --- | --- | --- | --- |
| 0    | x   | x   | x   | x   |
| 1    | x   |     |     | x   |
$$E = \not g.\not b$$
### 3.
Les manettes sont petite ou sans fil
### 4.
on constate que : $\lnot E = g.b$

Ce sont donc les grandes manettes à brancher qu'il faudrait supprimer.
## Exercice 2

### Partie A

#### 1/ 
En se basant sur les [[Systeme_de_numeration]], on peut convertir les écritures décimal en hexadécimal :
$$165/16 = 10 (\text{reste}\ \ 5)$$
$$165_{10} = A5_{16}$$
$$209/16 = 13 (\text{reste} \ \ 1)$$
$$209_{10} = D1_{16}$$
$$82/16 = 5 (\text{reste} \ \ 2)$$
$$82_{10} = 52_{16}$$
donc :
$$\begin{bmatrix} 165\\209\\82 \end{bmatrix}_{10} = \begin{bmatrix} A5\\D1\\52 \end{bmatrix}_{16}$$
#### 2/
**D** en hexadécimal correspond à 13 en décimal.
donc $D4_{16} = 13 * 16^1 + 4 * 16^0 = 208 + 4 = 212_{10}$
$$\begin{bmatrix} D4\\73\\D4 \end{bmatrix}_{16} = \begin{bmatrix} 212\\115\\212 \end{bmatrix}_{10}$$
#### 3/
Il y a en tout $256^3$ possibilité, ce qui fait $16777216$ 

Ce codage utilisa 8 bits par couleur.

### Partie B
#### 1.
##### a. 
$$M * C = S$$
##### b.
$$\begin{bmatrix} \frac{1}{3}&\frac{1}{3}&\frac{1}{3}\\1&-1&0\\-\frac{1}{2}&-\frac{1}{2}&1 \end{bmatrix} * \begin{bmatrix} 150\\90\\210 \end{bmatrix} = \begin{bmatrix} 150\\60\\90 \end{bmatrix}$$
#### 2.
##### a.
$$N * M = \begin{bmatrix} 1&\frac{1}{2}&-\frac{1}{3}\\1&-\frac{1}{2}&-\frac{1}{3}\\1&0&\frac{2}{3} \end{bmatrix} * \begin{bmatrix} \frac{1}{3}&\frac{1}{3}&\frac{1}{3}\\1&-1&0\\-\frac{1}{2}&-\frac{1}{2}&1 \end{bmatrix} = \begin{bmatrix} 1&0&0\\0&1&0\\0&0&1 \end{bmatrix}$$
On obtient une matrice identité
##### b.
On en déduit que $M$ est l'inverse de $N$ et inversement
#### 3.
##### a.
Si $M * C =S$ alors $N * M * C = N * S$, donc $I_3 * C = N = S$, et donc $C = N * S$
##### b.
$$C = N.S = \begin{bmatrix} 1&\frac{1}{2}&-\frac{1}{3}\\1&-\frac{1}{2}&-\frac{1}{3}\\1&0&\frac{2}{3} \end{bmatrix} * \begin{bmatrix} 120\\100\\-90 \end{bmatrix} =  \begin{bmatrix} 200\\100\\60 \end{bmatrix}$$
Les intensité RGB sont $\begin{bmatrix} 200\\100\\60 \end{bmatrix}$
## Exercice 3
### Partie A
#### 1.
On a $66 * 7 \equiv $