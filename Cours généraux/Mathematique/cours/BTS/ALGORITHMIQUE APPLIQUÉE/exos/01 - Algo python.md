Ce document est basé sur les exercice présent dans le document [[Python arithmétique.pdf|ici]]  

### Écrire un algorithme qui prend en entrée deux nombres entiers a et b, et calcule le quotient et le reste de la division euclidienne de a par b.

```python
a = int(input("Veuillez entrer un entier : "))  # on récupere un entier  
b = int(input("Veuillez entrer son diviseur : "))  # on récupere son diviseur  
q = int(a / b)  # q devient le quotient de a par b  
r = a % b  # r devient le reste de la divison de a par b  
print("Le quotient de ", a, "et ", b, "est ", q, ", sont reste est ", r)
```

### Écrire un algorithme qui prend en entrée deux nombres entiers a et b, et calcule leur plus grand diviseur commun (PGCD) en utilisant l'algorithme d'Euclide

```python
a = int(input("Veuillez entrer un entier : "))  # on récupere un entier  
b = int(input("Veuillez entrer son diviseur : "))  # on récupere son diviseur  
r = 1  # instance de la variable r

if a < b:  # si a est plus petit que b, alors a devien b et b devien a
    z = a  
    a = b  
    b = z

while r != 0:  # tant que r n'est pas égal à 0, faire cette boucle :  
    r = a % b  # r devient le reste de la division de a par b  
    if a > b:  # si a est plus grand que b alors a prend la valeur de b et b prend la valeur de r
        a = b  
        b = r  
    else:  # sinon b prend la valeur de r  
        b = r  
  
print("le PGCD est", a)
```

### Écrire un algorithme qui prend en entrée deux nombres entiers a et b, et calcule leur plus petit multiple commun (PPCM) en utilisant la formule : PPCM(a, b) = (a * b) / PGCD(a, b).

```python
a = c = int(input("Veuillez entrer un entier : "))  # on récupere un entier  
b = d = int(input("Veuillez entrer son diviseur : "))  # on récupere son diviseur  
r = 1  # instance de la variable r  
  
if a < b:  # si a est plus petit que b, alors a devien b et b devien a  
    z = a  
    a = b  
    b = z  
  
while r != 0:  # tant que r n'est pas égal à 0, faire cette boucle :  
    r = a % b  # r devient le reste de la division de a par b  
    if a > b:  # si a est plus grand que b alors a prend la valeur de b et b prend la valeur de r  
        a = b  
        b = r  
    else:  # sinon b prend la valeur de r  
        b = r  
  
ppcm = (c * d) / a  # Calcule du PPCM
  
print("Le PPCM est : ", ppcm)
```

### Écrire un algorithme qui prend en entrée un nombre entier n, et trouve le plus petit nombre premier qui est strictement supérieur à n.

```python
import math  
a = float(input("Nombre à arrondire au supérieur : "))  
  
print(math.ceil(a))
```