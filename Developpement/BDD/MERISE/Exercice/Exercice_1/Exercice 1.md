Dans un bibliothèque il faut:
- retrouver l'auteur
- retrouver le pays de naissance de l'auteur
- Notre bibliothèque peut posséder plusieurs exemplaire d'un même livre
- Chaque livre appartient à un et un seul type
- Les adhérant peuvent réaliser plusieurs emprunts

## MCD
![[Pasted image 20231205094938.png]]
## MLD
Auteur (**id_a_Auteur**, nom_a_Auteur, prenom_a_Auteur, dat_naissance_a_Auteur, `#id_p_Pays`)

Livre (**id_l_Livre**, titre_l_Livre, annee_l_Livre, resume_l_Livre, `#id_t_Type_livre`)   

Type_livre (**id_t_Type_livre**, libelle_t_Type_livre)   

Exemplaire (**ref_e_Exemplaire**,` #id_l_Livre`, `#id_ed_Edition`)   

Edition (**id_ed_Edition**, nom_ed_Edition)   

Pays (**id_p_Pays**, nom_p_Pays)   

Inscrit (**id_i_Inscrit**, nom_i_Inscrit, prenom_i_Inscrit, date_naissance_i_Inscrit, 
rue_i_Inscrit, ville_i_Inscrit, cp_i_Inscrit, email_i_Inscrit, tel_portable_i_Inscrit)  

Emprunt (**id_em_Emprunt**, date_em_Emprunt, delais_em_Emprunt,` #ref_e_Exemplaire`, `#id_i_Inscrit`)   

rediger (**id_l_Livre**, **id_a_Auteur**)