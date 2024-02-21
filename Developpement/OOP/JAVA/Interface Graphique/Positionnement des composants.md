## Les gestionnaires de mise en page

### Le gestionnaire de mise en page FlowLayout

Ce gestionnaire de mise en page est certainement le plus simple à utiliser. Il est associé par défaut à un composant JPanel. Sa stratégie de placement des composants consiste à les placer les uns à la suite des autres sur une ligne jusqu’à ce qu’il n’y ait plus de place sur cette ligne. 
Après le remplissage de la première ligne, les composants suivants sont placés sur une nouvelle ligne et ainsi de suite. C’est l’ordre d’ajout des composants sur le conteneur qui détermine leurs positions sur les différentes lignes. Chaque composant est séparé horizontalement de son voisin par un espace de cinq pixels par défaut et chaque ligne de composants est séparée de sa voisine par un espace de cinq pixels par défaut également. Lorsque ce gestionnaire place les composants, il les aligne par défaut sur le centre du conteneur. 
Tous ces paramètres peuvent être modifiés pour chaque gestionnaire de mise en page **FlowLayout**. Vous pouvez le faire dès la création du **FlowLayout** en indiquant dans le constructeur les informations correspondantes. Trois constructeurs sont disponibles pour cette classe. Le premier n’attend aucun argument et crée un **FlowLayout** avec les caractéristiques par défaut décrites ci-dessus. Le deuxième attend comme argument une des constantes suivantes permettant de spécifier le type d’alignement utilisé.

- FlowLayout.CENTER : chaque ligne de composant est centrée dans le conteneur (valeur par défaut).
    
- FlowLayout.LEFT : chaque ligne de composant est alignée sur la gauche du conteneur.
    
- FlowLayout.RIGHT : chaque ligne de composant est alignée sur la droite du conteneur.
    

Le dernier constructeur disponible attend comme arguments deux entiers en plus de la constante indiquant l’alignement. Ces deux entiers indiquent l’espacement horizontal et vertical entre les composants. La ligne de code suivante crée un FlowLayout qui aligne les lignes de composants sur la gauche du conteneur, laisse un espace horizontal de cinquante pixels et un espace vertical de vingt pixels entre les composants.

```java
FlowLayout fl = new FlowLayout(FlowLayout.LEFT,50,20);
```

Si vous ne créez pas vous-même de **FlowLayout** mais que vous utilisez celui fourni par défaut avec un **Jpanel**, vous pouvez intervenir sur ces paramètres de fonctionnement avec les méthodes suivantes :

- setAlignment : pour spécifier l’alignement des composants.
    
- setHgap : pour spécifier l’espacement horizontal entre les composants.
    
- setVgap : pour spécifier l’espacement vertical entre les composants.
    

Il est dans ce cas nécessaire d’obtenir une référence sur le FlowLayout associé au JPanel en utilisant la méthode getLayout de celui-ci. Une opération de transtypage est dans ce cas obligatoire pour pouvoir utiliser les méthodes de la classe FlowLayout sur la référence obtenue. En effet, la méthode getLayout retourne une variable de type LayoutManager, le super-type de tous les types de gestionnaire de présentation.

```java
    //Définition des caractéristiques du LayoutManager
        LayoutManager lm = pano.getLayout();
        if(lm instanceof FlowLayout)
        {
            // si le LayoutManager est un FlowLayout
            // on effectue un transtypage / conversion / cast
            FlowLayout fl = (FlowLayout) lm;
            fl.setAlignment(FlowLayout.LEFT);
            fl.setHgap(50);
            fl.setVgap(20);
        }
```