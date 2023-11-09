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