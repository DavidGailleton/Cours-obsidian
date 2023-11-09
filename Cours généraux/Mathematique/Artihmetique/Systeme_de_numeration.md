## Bases
### Base 10
Le système de numération décimal moderne utilise 10 symboles, qui sont les 10 chires : **0**, **1**,
**2**, **3**, **4**, **5**, **6**, **7**, **8** et **9**.
### Base 2
Le système binaire ou base 2 n'utilise que deux chiffres, deux symboles : **0** et **1**. Ce système
sert en particulier en électronique et en informatique, puisque l'électronique numérique ne sait
représenter que deux valeurs (correspondant à deux plages de tension).
La base 2 est la plus petite base envisageable. Un chiffre binaire est appelé bit en informatique,
ce qui est la contraction de binary digit, autrement dit chiffre binaire en anglais.
### Base 16
Le système hexadécimal est l'écriture dans la base 16. Les chiffres de la base 16 s'obtiennent
en complétant 0, 1, . . .9 avec les premières lettres de l'alphabet. Ainsi les symboles utilisés
comme chiffres pour la base 16 sont :
**0**, **1**, **2**, **3**, **4**, **5**, **6**, **7**, **8**, **9**, **A**, **B**, **C**, **D**, **E**, et **F**.
## Conversion
### Base 2
#### En base 10
Pour convertir un chiffre binaire en base décimal, on compte de droite a gauche les valeurs du chiffres en augmentant la puissance de 2 à chaque fois.

Exemple : 
*1001110* on le compte de droite a gauche avec le puissance 2<sup>6</sup> + 0<sup>5</sup> + 0<sup>4</sup> + 2<sup>3</sup>+ 2<sup>2</sup>+ 2<sup>1</sup>+ 0<sup>0</sup> 
Ce qui nous donne 78 en base 10  

0 = 0
1 = 1
2 = 10
3 = 11
4 = 100
5 = 101
6 = 110
7 = 111
8 = 1000
9 = 1001
10 = 1010
11 = 1011
12 = 1100
13 = 1101
14 = 1110
15 = 1111

#### En base 16
La convertion en base 16 est la même chose que pour la convertion en base 10, a la différence que la base 16 correspond en binaire à **4 bit** 

Exemple: 
1101 0111 = 2<sup>3</sup>+ 2<sup>2</sup>+ 0<sup>1</sup>+ 2<sup>0</sup> **ET** 0<sup>3</sup>+ 2<sup>2</sup>+ 2<sup>1</sup>+ 2<sup>0</sup> soit en Hexadécimal **D7**

0 = 0
1 = 1
2 = 10
3 = 11
4 = 100
5 = 101
6 = 110
7 = 111
8 = 1000
9 = 1001
A= 1010
B = 1011
C = 1100
D = 1101
E = 1110
F = 1111

### Base 10
Les conversion de la base 10 en d'autre bases se font simplement par [[Division euclidienne]]
#### en base 2
Pour la conversiton en base 2 il suffit simplement d'éffecctuer des vision euclidienne successive par 2, Le reste sera la valeur en base 2 :

29 / 2 = 14 reste 1
14 / 2 = 7 reste 0
7 / 2 = 3 reste 1
3 / 2 = 1 reste 1
1 / 2 = 0 reste 1

Donc **29** en base 10 est égal à **10111** en base 2

#### en base 16
Pour la conversion en base 16 on utilise le même principe

465 / 16 = 29 reste 1
29 /16 = 1 reste 13
1 / 16 = 0 reste 1
Donc **465** en base 10 est égal a **1D1** en base 16

### Base 16
#### en base 2
Pour convertire de la base 16 en base 2 on fait simplement l'inverse de [[#En base 16|base 2 en base 16]], c'est a dire transformer chaque caractère en son équivalent en **4 bit** 

**4FA** sera égal **0100 1111 1010**

#### en base 10
On peut convertir un nombre hexadécimal en décimal en additionnant les chiffres multipliés par leur poids (puissance de 16 associée).

E13A sera égal à 14x16<sup>3</sup> + 1x16<sup>2</sup> + 3x16<sup>1</sup> + 10x16<sup>0</sup> = 57 344 + 512 + 160 + 10 = 57658

## Arrondi et de précision
Tout nombre décimal n'a pas nécessairement une écriture finie en binaire. Il est
donc important de se pencher sur les notions d'arrondi et de précision.

Considérons le nombre 23,45825. Il existe plusieurs façon de l'arrondir :
-  arrondi à l'entier près : 23,
	-  arrondi (au plus proche) à 10<sup>-2</sup> près : 23,46,
-  arrondi par défaut à 10<sup>-2</sup> près : 23,45,
-  arrondi par excès à 10<sup>-3</sup> près : 23,459,
-  arrondi avec une précision de 3 chiffres significatifs : 23,5.

On peut aussi arrondir des nombres écrits dans d'autres bases :
-  1001, 01112 arrondi à l'entier près vaut 10012.
-  11, 111112 arrondi avec une précision de 3 chiffres signifcatifs vaut 11; 12.
-  1001, 101112 arrondi avec une précision de 3 chiffres significatifs vaut 1010.
-  A134B, C516 arrondi à l'entier près vaut A134C16.
-  A134B, C516 arrondi avec une précision de 3 chiffres significatifs vaut A130016.

## Opérations sur les entiers naturels

### Addition binaire

Pour additionner deux entiers écrits en binaire, il suffit de savoir que : 
-  0 + 0 = 0,
-  0 + 1 = 1 + 0 = 1,
-  1 + 1 = 10,
-  1 + 1 + 1 = 11.
Pour effectuer l'addition binaire, on procède comme pour une addition décimale, en
utilisant les égalités précédentes, et en tenant compte des éventuelles retenues.

**Remarque**: On peut vérifier les résultats des additions binaires en repassant en décimal.

**Remarque**: Pour calculer à la main des additions de nombres hexadécimaux, on peut convertir
les nombres en binaires, puis faire l'addition, puis reconvertir le résultat en hexadécimal.

### Soustraction binaire
La soustraction fonctionne avec le même principe que l'[[#Addition binaire]].
- 111 - 1 = 110
- 110 - 1 = 101
- 101 - 1 = 11

### Multiplication binaire par une puissance de 2
Soit *n* un entier naturel. Multiplier un entier binaire par 2<sup>n</sup> revient à ajouter *n* zéros à
droite du nombre.
1011 x 2<sup>4</sup> = 1011 x 10000 = 10110000

### Division binaire par une puissance de 2
Soit *n* un entier naturel. Lorsqu'on réalise la division euclidienne d'un entier binaire par
2<sup>n</sup>, on obtient :
-  un reste formé de *n* chiffres les plus à droite du nombre,
-  un quotient formé par les chiffres restants.

**Exemple**: 1011001 / 2<sup>3</sup> = 1011 et le reste est 001