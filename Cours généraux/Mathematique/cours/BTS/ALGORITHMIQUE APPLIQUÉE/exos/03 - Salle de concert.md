[[Maths pour linformatique Algorithme-1.pdf|Exercice (page 19)]]

## A1
```python
a = int(input("Combien de place voulez vous acheter ? "))  
  
p = a * 20  
  
if  a >= 3:  
    p = p * 0.9  
  
print("Le prix à payer est de", p, "€")
```

## A2

```python
a = int(input("Combien de place voulez vous acheter ? "))  
e = str(input("Etes vous étudiant ? (y pour oui, n pour non) "))  
  
p = a * 20  
  
if e == "y":  
    p = p * 0.75  
  
print("Le prix à payer est de", float(p), "€")
```

## A3

