Un dictionnaire est une structure de données qui enregistre des données dans des **paires clés-valeurs**. Voici un exemple d’une clé et d’une valeur :  

`"responsable_de_campagne": "Jeanne d'Arc"`

La **clé** est   `"responsable_de_campagne"`  et la **valeur** est   `"Jeanne d'Arc"`  .

Les dictionnaires sont indiqués par des accolades `{}`  au début et à la fin. Chaque paire clé-valeur comprend un deux-points  `:`  placé entre la clé et la valeur, et une virgule  `,`   à la fin. Chaque dictionnaire doit être composé de clés uniques.

Dans le diagramme ci-dessous, le dictionnaire défini a trois éléments, et chaque élément est une paire clé-valeur :
![[16827780421019_image9.png]]
## Créez un dictionnaire

Imaginons que vous vouliez enregistrer des informations à propos d’une nouvelle campagne pour une entreprise de nourriture pour chien. Vous allez probablement devoir sauvegarder un nom de campagne, des dates de début et de fin, le nom d’un responsable de campagne, et des influenceurs importants. Vous pouvez sauvegarder toutes ces informations dans une variable avec un dictionnaire.

Pour enregistrer tout cela, vous pouvez sauvegarder un dictionnaire comme ça :
```python
nouvelle_campagne = {
"responsable_de_campagne": "Jeanne d'Arc",
"nom_de_campagne": "Campagne nous aimons les chiens",
"date_de_début": "01/01/2020",
"influenceurs_importants": ["@MonAmourDeChien", "@MeilleuresFriandisesPourChiens"]
}
```

Vous pouvez aussi créer un nouveau dictionnaire avec des accolades vides  `{}`  ou la fonction  `dict()`, et avec des paires clés-valeurs comme indiqué ci-dessous :
```python
taux_de_conversion = {}
taux_de_conversion['facebook'] = 3.4
taux_de_conversion['instagram'] = 1.2
taux_de_conversion = dict()
taux_de_conversion['facebook'] = 3.4
taux_de_conversion['instagram'] = 1.2
```
## Accédez à une valeur dans un dictionnaire

Pour accéder aux différentes valeurs, vous pouvez utiliser la clé pour chacune des paires clés-valeurs.
```python
>>> nouvelle_campagne['responsable_de_campagne']
"Jeanne d'Arc"
>>> taux_de_conversion['facebook']
3.4
```
## Réalisez des opérations courantes avec les dictionnaires

Comme pour les listes, plusieurs méthodes (ou opérations) intégrées à Python vous permettent de manipuler les données dans les dictionnaires.

### Ajoutez une paire clé-valeur

Pour ajouter une paire clé-valeur à un dictionnaire, ajoutez juste une nouvelle clé dans le dictionnaire existant. Si la clé existe déjà, vous l’écraserez en définissant une valeur. Le code suivant crée un dictionnaire appelé   `infos_labradoodle`  , et enregistre des informations à propos du poids et de l’origine des labradoodles, un croisement de chiens: 
```python
infos_labradoodle = {
    "poids": "13 à 16 kg",
    "origine": "États-Unis"
}
```
Pour ajouter une nouvelle paire clé-valeur, comme le nom scientifique du labradoodle, ajoutez simplement :
```python
infos_labradoodle['nom_scientifique'] = "Canis lupus familiaris"

>>> print(infos_labradoodle)
{'poids': '13 à 16 kg', 'origine': 'États-Unis', 'nom_scientifique': 'Canis lupus familiaris'}
}
```
Si vous écrivez   `infos_labradoodle["poids"] = "45 kg"`  , la valeur existante sera écrasée, et le résultat sera donc : 
```python
>>> infos_labradoodle["poids"]
"45 kg"
```

### Supprimez une paire clé-valeur

Pour supprimer une paire clé-valeur, vous pouvez utiliser le mot-clé  `del`  et la clé que vous voulez supprimer, ou encore la méthode   `pop`  . Pour supprimer la paire clé-valeur  `"origine"`  de la paire  `clé-valeur`  , écrivez :
```python
>>> del infos_labradoodle["origine"]
>>> print(infos_labradoodle)
{ "poids": "13 à 16 kg",
"nom_scientifique": "Canis lupus familiaris"}
```
### quelque methode
Voici encore quelques méthodes couramment utilisées pour manipuler des dictionnaires :

|   |   |
|---|---|
|keys()|​​Retourne une vue sur les clés du dictionnaire.|
|values()|Retourne une vue sur les valeurs du dictionnaire.|
|items()|Retourne une vue sur les couples (clé, valeur) du dictionnaire.|
|get(clé)|Retourne la valeur associée à la clé spécifiée. Si la clé n'est pas présente dans le dictionnaire, retourne la valeur `None`  .|
|pop(clé)|Supprime la clé spécifiée et retourne la valeur associée. Si la clé n'est pas présente dans le dictionnaire, retourne la valeur `None`  .|
|clear()|Supprime tous les éléments du dictionnaire.|
