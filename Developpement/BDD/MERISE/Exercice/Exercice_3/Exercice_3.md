Une garage automobile souhaite gérer son stock de pièces. 
Chaque pièce est identifiée par une référence, une catégorie (carosserie, mécanique, électricité, etc.), une date de récupération et un prix de vente. 
On souhaite également pouvoir établir une correspondance entre les pièces et les véhicules pour lesquels elles conviennent, ces véhicules étant repérés par marque, modèle et année.

## MCD
![[Pasted image 20231205111640.png]]
## MLD
convient à (**#id_type_piece**, **#id_modele**)

Pieces (**id_piece**, etat, date recup, `#id_type_piece`)

Types_piece (**iod_type_piece**, ref_constructeur, prix, `#id_categorie`)

Modèles (**id_modele**, nom_modele, annee_modele, `#id_marque`)

Categories (**id_categorie**, intitule_categorie)

Marques (**id_marque**, nom_marque)