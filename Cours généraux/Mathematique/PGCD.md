## Définition
En arithmétique élémentaire, le **plus grand commun diviseur** ou **PGCD** de deux nombres entiers non nuls est le plus grand entier qui les divise simultanément.

Par exemple, le PGCD de 20 et de 30 est 10, puisque leurs diviseurs communs sont 1, 2, 5 et 10

## Algorithme

### Algorithme d’Euclide
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
