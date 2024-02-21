## Notion
Pour comprendre les congruences, nous avons besoin d’un entier naturel non nul $n$, et de deux entiers relatifs $a$ et $b$.
Si $a – b$ est divisible par $n$, on dit que $a$ et $b$ sont congrus modulo $n$ et on note :$$a ≡ b [n]$$
On dit aussi que **$a$ est congru à $b$ modulo $n$.**

### Exemple
$15 ≡ 7 [4]$ car $15 – 7 = 8$, qui est divisible par 4.  
$32 ≡ 2 [3]$ car $32 – 2 = 30$, qui est divisible par 3.  
En revanche, 15 n’est pas congru à 3 module 5 car $15 – 3 = 12$, qui n’est pas divisible par 5.

## Propriété
Dans tout ce qui suit, n est un entier naturel non nul, a et b sont des entiers relatifs.
### la transitivité
On considère trois entiers relatifs a, b et c, et un entier naturel n non nul.  
On a alors : $$\text{Si} \; a≡b[n] \; \text{et} \; b≡c[n] \text{, alors} \; a≡c[n]$$
### **Relation de transitivité**
Il est possible d'effectuer des opération sur les congruence. On pourras utiliser l'**addition**, la **soustraction**, la **multiplication** et la **puissance** (Il est **Interdit** d'utiliser la division): 
$$a+a'≡b+b'[n]$$
$$a-a'≡b-b'[n]$$
$$a*a'≡b*b'[n]$$
$$a^p≡b^p[n], \forall p \in \Bbb{N}$$
**on peut ajouter ou soustraire autant de fois que l’on veut le modulo.**
Ainsi, si on a par exemple :  
$a ≡ 40 [7]$, on peut dire $a ≡ 33 [7]$, $a ≡ 26 [7]$, $a ≡ 19 [7]$, etc… (on enlève 7 à chaque fois).  
On peut aussi dire $a ≡ 47 [7]$, $a ≡ 54 [7]$, etc… (on rajoute 7 à chaque fois).