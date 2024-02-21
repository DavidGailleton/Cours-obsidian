## For
La boucle`for` est le type de boucle centrale dans Python. Une boucle`for` est utilisée pour **itérer** sur une séquence. Ça peut être une liste, un tuple, un dictionnaire ou même une chaîne de caractères. Avec une boucle`for` , vous pouvez exécuter le même code pour chaque élément dans cette séquence. 

Avec Python, c’est très facile de créer des boucles. Si vous voulez afficher tous les éléments dans une liste, le code ressemblera à ça :
```python
races_de_chien = ["golden retriever", "chihuahua", "terrier", "carlin"]
for chien in races_de_chien:
    print(chien)
```
Dans ce code, chaque élément dans   `races_de_chien`  sera affiché dans le terminal.
![[16827860942511_image6.png]]
Pour boucler un certain nombre de fois, vous pouvez utiliser la [[Fonction]]  `range()`  . Elle renverra une séquence de nombres qui vont de 0 à un nombre de fin déterminé.
```python
for x in range(5):
    print(x)
```
Ce code affichera 0, 1, 2, 3, 4 en séquence.

## While
La boucle   `for`  vous permet d’exécuter du code un nombre spécifique de fois, alors que la **boucle**  **`while`**  continue de s’exécuter jusqu’à ce qu’une certaine **condition** soit remplie.

Dans [[Condition]], vous avez découvert des conditions, ou instructions, qui évaluent si une expression est vraie ou fausse. C’est la même chose ici : le code dans l’instruction   `while`  s’exécute jusqu’à ce que la condition devienne fausse.

```python
capacite_maximale = 10
capacite_actuelle = 3
while capacite_actuelle < capacite_maximale:
    capacite_actuelle += 1
```
Comme cette   `capacite_actuelle`  commence à 3, ce code s’exécute 7 fois jusqu’à ce que   `capacite_actuelle`  atteigne 10.
![[16827886925394_image16.png]]
## Quand utiliser for ou while

> Dans quel cas utilise-t-on généralement une boucle  `for`  et dans quel cas utilise-t-on une boucle  `while` ?

On utilise généralement une boucle  `for`  lorsqu'on connaît à l'avance le nombre d'itérations à effectuer, et une boucle  `while`  lorsqu'on ne connaît pas à l'avance le nombre d'itérations à effectuer, et que la boucle doit s'arrêter lorsque la condition spécifiée est satisfaite.

## `break`  et `continue`
Il est courant d'utiliser des boucles pour répéter une série d'instructions plusieurs fois. Parfois, il peut être utile d'interrompre ou de sauter une itération dans la boucle. C'est là que les instructions `break`  et `continue`  entrent en jeu.

### break
L'instruction `break`  permet de **sortir** d'une boucle prématurément. Elle est souvent utilisée lorsqu'une condition est rencontrée, et que l'on souhaite **arrêter** la boucle avant qu'elle ne se termine normalement. 

Voici un exemple :
```python
for i in range(10):
    if i == 5:
        break
    print(i)
```
### continue
L'instruction  `continue`  permet de passer à la prochaine itération de la boucle, sans exécuter le reste du code présent dans la boucle pour l'itération en cours. Elle est souvent utilisée lorsqu'une condition est rencontrée, mais que l'on souhaite continuer la boucle sans exécuter le reste du code.
```python
liste = [1, 2, 3, 4, 5]
# Boucle for sur la liste
for element in liste:
    if element == 3:
        # Si l'élément vaut 3, on passe à l'itération suivante sans exécuter le reste du code
        continue
    # Dans tous les autres cas, on exécute le reste du code
    print(element)
```
	Afficher dans la console : 1 2 4 5

