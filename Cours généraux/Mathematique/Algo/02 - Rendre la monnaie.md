[[Maths pour linformatique Algorithme-1.pdf|Exercice (Page 14)]]

## 1.

```python
a = int(input("Saissez un nombre de centime: "))  
  
b = a / 2  
c = a % 2  
  
print(int(b), " pièce de 2 centimes")  
print(int(c), " pièce de 1 centime")
```

## 2.

```python
a = int(input("Saissez un nombre de centime: "))  
  
b = a / 50  
r = a % 50  
c = r / 20  
r = r % 20  
d = r / 10  
r = r % 10  
e = r / 5  
r = r % 5  
f = r / 2  
r = r % 2  
  
print(int(b), " pièce de 50 centimes")  
print(int(c), " pièce de 20 centimes")  
print(int(d), " pièce de 10 centimes")  
print(int(e), " pièce de 5 centimes")  
print(int(f), " pièce de 2 centimes")  
print(int(r), " pièce de 1 centime")
```