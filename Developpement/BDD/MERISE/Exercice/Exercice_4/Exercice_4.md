Un aquarium souhaite gérer ses petites bêtes: 
- Il dispose pour cela de plusieurs bassins, répartis dans plusieurs pièces. 
- Des animaux de différentes espèces sont achetés, immatriculés et disposent d'un suivie médical personnalisé - on garde donc la date et la nature des soins dont ils bénéficient.
- Les animaux sont mélangés dans les bassins, et il arrive qu'on les déplace- la encore, on souhaite savoir à quelle date un animal donné a quitté tel bassin pour être placé dans un tel autre.
- Les biologiste classent les animaux selon une arborescence à quatre niveaux du plus général au plus particulier: ordre, famille, genre, espèce. Il va de soi que chaque animal de l'aquarium doit être correctement identifié dans cette arborescence.

## MCD
![[Pasted image 20231205120450.png]]
## MLD
Pieces (**id_pce**, no_pce)   
Bassins (**id_bassin**, no_bassin, `#id_pce`)   
Especes (**id_espece**, nom_esp)   
Animaux (**id_animal**, date_naissance, date_achat, `#id_espece`)   
Soins (**id_soin**, type_soin)   
Genres (**id_genre**, nom_genre, `#id_famille`)   
Familles (**id_famille**, nom_famille, `#id_ordres`)   
Ordres (**id_ordres**, nom_ordres)   
Logé (**id_bassin**, **id_animal**, date_entree, date_sortie)   
Soigné (**id_animal**, **id_soin**, date)   
Membre_du_genre (**id_espece**, **id_genre**, id_genre, nom_genre)