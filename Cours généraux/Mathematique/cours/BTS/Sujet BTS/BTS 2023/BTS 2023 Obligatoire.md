## Exercice 1
### Q 1
C: 7E7
### Q 2
C: $10101_2$
### Q 3

### Q 4

### Q 5
C: Bijective
## Exercice 2
### Partie A
#### 1.
![[Pasted image 20240222161658.png]]
#### 2
##### a
$$P^² = \begin{bmatrix} 
2 & 0 & 1 \\
1 & 0 & 0 \\
1 & 0 & 1
\end{bmatrix}$$
##### b
Un seul chemin de Longueur 2 part de B : $B \rightarrow C \rightarrow A$
#### 3
Pour trouver $\hat P$ il faut en premier temps trouver $P^3$ :
$$P^3 = \begin{bmatrix}
3 & 0 & 2 \\
1 & 0 & 1\\
2 & 0 & 1
\end{bmatrix}$$
$$\hat P = \begin{bmatrix}
1 & 0 & 1 \\
1 & 0 & 1 \\
1 & 0 & 1 
\end{bmatrix}$$
### Partie B
#### 1
##### a
Le degré entrant du sommet C est de 2 comme on peut le voir dans la matrice $P$.
##### b
Le degré sortant du sommet C est de 1 comme on peut le voir dans la matrice $P$.
#### 2.
**Fonction** Degré_sortant (M, s)
	deg $\leftarrow$ 0
	Pour j allant de 1 a 3 **Faire**
		**Si** $m_{sj}$  < 4 &&  $m_{sj}$ <= 0 **Faire**
				n = 0
			pour n  < 3
				deg + $m_{sjni}$ 
				n +1
		Fin de **Si**
	Fin de **Pour**
Retourner deg

### Exercice 3
