Les collections sont des classes qui permettent de stocker des objets. Il existe plusieurs types de collections:
- [[Listes (list)]]
- [[Files (queue)]]
- [[Piles (Stack)]]
- [[Ensembles (Set)]]
- [[Tableaux associatifs (Map)]]

Les applications ont très fréquemment besoin de manipuler de grandes quantités d’informations. De nombreuses structures sont disponibles pour faciliter la gestion de ces informations. Elles sont regroupées sous le terme collection. Comme dans la vie courante, il y a différents types de collections et de collectionneurs. Il peut y avoir des personnes qui récupèrent toutes sortes de choses, mais qui n’ont pas d’organisation particulière pour les ranger, d’autres qui sont spécialisées dans la collection de certains types d’objets, les maniaques qui prennent toutes les précautions possibles pour pouvoir retrouver à coup sûr un objet...

Le langage Java propose différentes classes permettant de mettre en place plusieurs modes de gestion.

La première solution pour gérer un ensemble d’éléments est l’utilisation de tableaux. Cette solution a été décrite dans la section Les tableaux du chapitre Bases du langage. Bien que simple à mettre en œuvre, cette solution n’est pas très souple. Son principal défaut tient au caractère fixe de la taille d’un tableau. S’il n’y a plus de place pour stocker des éléments supplémentaires, il faut créer un nouveau tableau plus grand et y transférer le contenu du tableau précédent. Cette solution, lourde à mettre en œuvre, est consommatrice de ressources.

Le langage Java propose une vaste palette d’interfaces et de classes pour gérer facilement des ensembles d’éléments. Les interfaces décrivent les fonctionnalités disponibles alors que les classes implémentent et fournissent réellement ces fonctionnalités. Suivant le mode de gestion des éléments souhaité, on utilisera bien sûr la classe la plus adaptée. Cependant, les mêmes fonctionnalités de base doivent être accessibles, quel que soit le mode de gestion. Pour assurer la présence de ces fonctionnalités indispensables dans toutes les classes, celles-ci ont été regroupées dans l’interface Collection qui est par la suite utilisée comme interface de base. La hiérarchie des interfaces est représentée sur le diagramme ci-dessous.

![[Pasted image 20231003112315.png]]
