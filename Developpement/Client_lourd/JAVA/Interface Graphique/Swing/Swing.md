## La bibliothèque Swing

Cette bibliothèque a été conçue pour pallier les principales insuffisances de la bibliothèque AWT. Cette amélioration a été obtenue en écrivant entièrement cette bibliothèque en Java sans pratiquement faire appel aux services du système d’exploitation. Seuls quelques éléments graphiques (fenêtres et boîtes de dialogue) sont encore en relation avec le système d’exploitation. Pour les autres composants, c’est le code de la bibliothèque Swing qui détermine entièrement leurs aspects et comportements.

La bibliothèque Swing contient donc une quantité impressionnante de classes servant à redéfinir les composants graphiques. Il ne faut cependant pas penser que la bibliothèque Swing rend complètement obsolète la bibliothèque AWT. Beaucoup d’éléments de la bibliothèque AWT sont d’ailleurs repris dans la bibliothèque Swing.

### Les composants graphiques SWING et java

La conception de l’interface graphique d’une application consiste essentiellement à créer des instances des classes représentant les différents éléments nécessaires, modifier les caractéristiques de ces instances de classe, les assembler et prévoir le code de gestion des différents événements pouvant intervenir au cours du fonctionnement de l’application. Une application graphique est donc constituée d’une multitude d’éléments superposés ou imbriqués. Parmi ces éléments, l’un d’entre eux joue un rôle prépondérant dans l’application. Il est souvent appelé conteneur de premier niveau. C’est lui qui va interagir avec le système d’exploitation et contenir tous les autres éléments. En général ce conteneur de premier niveau ne contient pas directement les composants graphiques mais d’autres conteneurs sur lesquels sont placés les composants graphiques. Pour faciliter la disposition de ces éléments les uns par rapport aux autres, nous pouvons utiliser l’aide d’un gestionnaire de mise en page. Cette superposition d’éléments peut être assimilée à une arborescence au sommet de laquelle nous avons le conteneur de premier niveau et dont les différentes branches sont constituées d’autres conteneurs. Les feuilles de l’arborescence correspondant aux composants graphiques.

Le conteneur de premier niveau étant l’élément indispensable de toute application graphique, nous allons donc commencer par étudier en détail ces caractéristiques et son utilisation puis nous étudierons les principaux composants graphiques.

### La conception d'une interface graphique

Nous avons vu un petit peu plus haut que toute application graphique est au moins constituée d’un conteneur de premier niveau. La bibliothèque Swing dispose de trois classes permettant de jouer ce rôle :

**JApplet** : représente une fenêtre graphique embarquée à l’intérieur d’une page html pour être prise en charge par un navigateur. Cette classe n’a plus d’utilité depuis la plateforme Java 11 car la technologie des applets y a été abandonnée.

**JWindow** : représente une fenêtre graphique la plus rudimentaire qui soit. Celle-ci ne dispose pas de barre de titre, de menu système, pas de bordure, c’est en fait un simple rectangle sur l’écran. Cette classe est rarement utilisée sauf pour l’affichage d’un écran d’accueil lors du démarrage d’une application (splash screen).

**[[JFrame]]** : représente une fenêtre graphique complète et pleinement fonctionnelle. Elle dispose d’une barre de titre, d’un menu système, d’une bordure, elle peut facilement accueillir un menu, c’est bien sûr cet élément que nous allons utiliser dans la très grande majorité des cas.