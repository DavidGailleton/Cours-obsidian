Il est possible de relier une entité à elle-même par une association, on parle dans ce cas-là d'association réflexive. 
Imaginons que l'on veuille connaître les inscrits qui sont mariés entre eux tout en conservant leur date de mariage, voici ce que l'on obtiendrait au niveau conceptuel :
![[Pasted image 20231207094149.png]]
Inscrit (**id_i**, nom_i, ... , tel_portable_i)
être marié (**id_epoux#**, **id_epouse#**, date_mariage_i)
