Définition : On appelle proposition tout énoncé dont on peut dire sans ambiguïté s'il est vrai ou faux

Notons P une proposition :
- Soit P est vraie: noté V
- Soit P est faux: noté F

On peut également le noté 0 ou 1 en boolean

## Négation
Une négation est le contraire d'un proposition: Si P est vrai alors sa négation est fausse et inversement

$2^{10} = 1024$ (V) alors que $2^{10} \neq 1024$ (F)

## Connecteur Binaire
Il permet de former 2 proposition pour en former qu'un seule.

### Conjonction

Connecteur Logique : **ET** ou **AND**
signe : $\land$

On appelle conjonction des proposition P et Q et l'on note : $P \land Q$

Table de vérité :

P | Q | $P \land Q$
:--: | :--: | :--: 
V | V | V
V | F | F
F | V | F
F | F | F

P | Q | $P \land Q$
:--: | :--: | :--: 
1 | 1 | 1
1 | 0 | 0
0 | 1 | 0
0 | 0 | 0
### Disjonction

Connecteur Logique : **OU** ou **OR**
signe : $\lor$

On appelle conjonction des proposition P et Q et l'on note : $P \lor Q$
Elle vrai si au moins un des 2 est vrai.


P | Q | $P \lor Q$
:--: | :--: | :--: 
V | V | V
V | F | V
F | V | V
F | F | F

P | Q | $P \lor Q$
:--: | :--: | :--: 
1 | 1 | 1
1 | 0 | 1
0 | 1 | 1
0 | 0 | 0
### Implication

Connecteur logique : **SI... alors...** 
Signe : $\Rightarrow$
A tout couple de proposition (P, Q) l'implication associe une nouvelle proposition : $P \Rightarrow Q$
qui n'est fausse que dans le seul cas où : la proposition **P est Vrai** et la proposition **Q est fausse**


P | Q | $P \Rightarrow Q$
:--: | :--: | :--: 
V | V | V
V | F | F
F | V | V
F | F | V

P | Q | $P \lor Q$
:--: | :--: | :--: 
1 | 1 | 1
1 | 0 | 0
0 | 1 | 1
0 | 0 | 1


### Equivalence
Soient P et Q deux proposition.
La proposition P est equivalent a Q 
notée : $P \iff Q$
(lue "P si et seulement si Q")
n'est vraie que si l'on a simultanément $P \Rightarrow Q \; \text{ET} \; Q \Rightarrow P$

P | Q | $P \Rightarrow Q$ | $Q \Rightarrow P$ | $P \iff Q$
:--: | :--: | :--: | :--: | :--:
V | V | V | V | V
V | F | F | V | F
F | V | V | F | F
F | F | V | V | V

#### Commutativité

Pour toutes proposition P et Q
$$P \lor Q \iff Q \lor P$$
$$P \land Q \iff Q \land P$$
#### Double distributivité
Pour toutes proposition P, Q et R
$$P \lor (Q\land R) \iff (P \lor Q) \land (P \lor R)$$

P | Q | R | $P \lor Q$ | $P \lor R$ | $(P \lor Q) \land (P \lor R)$ | $Q \land R$ | $P \lor (Q \land R)$
:--: | :--: | :--: | :--: | :--: | :--: | :--: | :--:
1 | 1 | 1 | 1 | 1 | 1 | 1 | 1
1 | 1 | 0 | 1 | 1 | 1 | 0 | 1
1 | 0 | 1 | 1 | 1 | 1 | 0 | 1
0 | 1 | 1 | 1 | 1 | 1 | 1 | 1
1 | 0 | 0 | 1 | 1 | 1 | 0 | 1
0 | 1 | 0 | 1 | 0 | 0 | 0 | 0
0 | 0 | 1 | 0 | 1 | 0 | 0 | 0
0 | 0 | 0 | 0 | 1 | 0 | 0 | 0

$$P \land (Q\lor R) \iff (P \land Q) \lor (P \land R)$$
#### Complémentarité

Pour toute proposition P
$P \lor (\lnot P)$ sera toujours **vrai**
$P \land (\lnot P)$ sera toujours **faux**


#### negation d'un proposition avec connecteurs