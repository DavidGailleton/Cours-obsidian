## Rappels

Un nombre pair : Si a est pair alors a = 2 x k avec k un entier
a= 0 mod(2)     ;      a= 0[2]     ;    se lit est congru à 0 modulo 2

#### Algo 1 : récupérer un nombre et indiquer s'il est pair ou non 
```python
a = int(input("Veuillez entrer un entier : "))  # on récupere un entier  
b = a % 2  # B devient le reste de la division euclidienne de a par 2  
if b == 0:  # on verifier que la valeur de b est bien 0  
    print("Cet entier est paire !")  # si s'en est un, alors l'entier est paire  
else:  
    print("Cet entier est impaire !")  # sinon il est impaire
```

#### Algo 2 : Récupérer deux nombres, il faut renvoyer le quotient et le reste de la division du premier nombre par le deuxième
```python
a = int(input("Veuillez entrer un entier : "))  # on récupere un entier  
b = int(input("Veuillez entrer son diviseur : "))  # on récupere son diviseur  
q = int(a / b)  # q devient le quotient de a par b  
r = a % b  # r devient le reste de la divison de a par b  
print("Le quotient de ", a, "et ", b, "est ", q, ", sont reste est ", r)
```

#### Algo 3 : Trouver le [[PGCD]] via un algorithme d'Euclide
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
#### Algo 4 : Trouver le [[PGCD]] via 